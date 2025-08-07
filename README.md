stages:
  - trigger-jenkins
  - dockerize

variables:
  JAR_NAME: "admin-0.0.1-SNAPSHOT.jar"
  DOCKER_IMAGE_NAME: "gfs-fos/admin-service"
  DOCKER_TAG: "latest"
  JENKINS_JOB_URL: "https://jenkins.company.com/job/your-job-name/buildWithParameters"
  JENKINS_USER: "$JENKINS_USER"
  JENKINS_API_TOKEN: "$JENKINS_API_TOKEN"

trigger_jenkins:
  stage: trigger-jenkins
  image: curlimages/curl:latest
  script:
    - echo "Triggering Jenkins job..."
    - >
      curl -X POST "${JENKINS_JOB_URL}?token=TRIGGER_TOKEN"
      --user "${JENKINS_USER}:${JENKINS_API_TOKEN}"
  allow_failure: false

docker_build:
  stage: dockerize
  image: docker:latest
  services:
    - docker:dind
  script:
    - echo "Waiting for Jenkins job to finish (manual wait or webhook recommended)"
    - echo "Downloading built JAR from Jenkins or Nexus..."
    - mkdir -p target
    - curl -u "${JENKINS_USER}:${JENKINS_API_TOKEN}" -O https://jenkins.company.com/job/your-job-name/lastSuccessfulBuild/artifact/target/${JAR_NAME}
    - docker build --build-arg JAR_NAME=${JAR_NAME} -t ${DOCKER_IMAGE_NAME}:${DOCKER_TAG} .




# Dockerfile
FROM fmk.nexus-ci.onefiserv.net/org/is/com.fiserv.issuer/fs-container-springboot-x86:3.0.8

USER root

ARG JAR_NAME
COPY target/${JAR_NAME} /app/apprapid.jar

RUN chgrp -R 0 /app && chmod -R g+rwX /app

VOLUME ["/app"]
WORKDIR /app

USER 1001

ENTRYPOINT ["java", "-Xmx1G",
            "-Dreactor.netty.http.server.accessLogEnabled=true",
            "-Djava.security.egd=file:/dev/./urandom",
            "-Duser.timezone=America/Toronto",
            "-jar", "/app/apprapid.jar"]







