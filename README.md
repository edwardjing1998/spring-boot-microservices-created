def modules = ['admin', 'assistant']

node {
  checkout scm
  def branch = env.BRANCH_NAME

  for (def module : modules) {
    dir(module) {
      echo "Building module: ${module}"
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

      if (branch ==~ /release.*/ && !(result.releaseVersion ==~ /.*-SNAPSHOT/)) {
        gfsProductServiceVersionUpdate(
          product: "gfs-fos-rapid-${module}-1",
          branch: 'release/RAPID-Rapid-microservices-Java',
          service: "gfs-fos-rapid-${module}-microservices",
          version: result.releaseVersion,
          repoUrl: 'https://gitlab.onefiserv.net/issuers/fos-modernization/plastic/rapid/RAPID-Rapid-microservices-Java.git'
        )
      }
    }
  }
}
