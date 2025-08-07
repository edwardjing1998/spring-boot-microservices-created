FROM fmk.nexus-ci.onefiserv.net/org/is/com.fiserv.issuer/fs-container-springboot-x86:3.0.8

USER root

COPY target/*-SNAPSHOT.jar /app/
RUN chgrp -R 0 /app && chmod -R g+rwX /app

VOLUME ["/app"]
WORKDIR /app

USER 1001

COPY /app/admin-0.0.1-SNAPSHOT.jar apprapid.jar

ENTRYPOINT ["java", "-Xmx1G",
            "-Dreactor.netty.http.server.accessLogEnabled=true",
            "-Djava.security.egd=file:/dev/./urandom",
            "-Duser.timezone=America/Toronto",
            "-jar", "/app/apprapid.jar"]


node {
  checkout scm
  def branch = env.BRANCH_NAME

  def result = gfsCloudPipelineV2(
        releaseOptions: '',
        emailTo: 'harishchander.baswapuram@fiserv.com',
        deployToQA: false,
        waitTimeForRegressions: '240',
        buildContainerImage: true,
        jdkVersion: 'jdk21',
        serviceType: 'springboot',
        dynamicScanId: ["9527dc24-ccc6-4e30-85dd-62c95d9c8b1b"]
      )
  // release version can be SNAPSHOT version if the pipeline was triggered  by scan schedule
  if(branch ==~ /release.*/ && !(result.releaseVersion ==~ /.*-SNAPSHOT/)) {
    print 'updating version in product helm yaml'
    gfsProductServiceVersionUpdate(
        product: 'gfs-fos-rapid-rapid-1',
        branch: 'release/RAPID-Rapid-microservices-Java',
        service: 'gfs-fos-rapid-rapid-microservices',
        version: result.releaseVersion,
        repoUrl: 'https://gitlab.onefiserv.net/issuers/fos-modernization/plastic/rapid/RAPID-Rapid-microservices-Java.git'
      )
  }
}
