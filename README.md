def modules = ['client-sysprin-reader']

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





Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/spring-expression/6.2.2/spring-expression-6.2.2.pom
Progress (1): 2.1 kB
                    
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/spring-expression/6.2.2/spring-expression-6.2.2.pom (2.1 kB at 5.3 kB/s)
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/io/micrometer/micrometer-observation/1.14.3/micrometer-observation-1.14.3.pom
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/io/micrometer/micrometer-observation/1.14.3/micrometer-observation-1.14.3.pom
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/io/micrometer/micrometer-observation/1.14.3/micrometer-observation-1.14.3.pom
Progress (1): 3.8 kB
                    
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/io/micrometer/micrometer-observation/1.14.3/micrometer-observation-1.14.3.pom (3.8 kB at 8.8 kB/s)
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/io/micrometer/micrometer-commons/1.14.3/micrometer-commons-1.14.3.pom
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/io/micrometer/micrometer-commons/1.14.3/micrometer-commons-1.14.3.pom
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/io/micrometer/micrometer-commons/1.14.3/micrometer-commons-1.14.3.pom
Progress (1): 3.4 kB
                    
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/io/micrometer/micrometer-commons/1.14.3/micrometer-commons-1.14.3.pom (3.4 kB at 7.6 kB/s)
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/org/springframework/boot/spring-boot-buildpack-platform/3.4.2/spring-boot-buildpack-platform-3.4.2.jar
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/com/fasterxml/jackson/module/jackson-module-parameter-names/2.18.2/jackson-module-parameter-names-2.18.2.jar
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/org/apache/httpcomponents/client5/httpclient5/5.4.1/httpclient5-5.4.1.jar
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/org/apache/httpcomponents/core5/httpcore5/5.3.1/httpcore5-5.3.1.jar
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/org/apache/httpcomponents/core5/httpcore5-h2/5.3.1/httpcore5-h2-5.3.1.jar
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/org/springframework/boot/spring-boot-loader-tools/3.4.2/spring-boot-loader-tools-3.4.2.jar
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/org/springframework/spring-core/6.2.2/spring-core-6.2.2.jar
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/org/springframework/spring-jcl/6.2.2/spring-jcl-6.2.2.jar
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/org/springframework/spring-context/6.2.2/spring-context-6.2.2.jar
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/org/springframework/spring-aop/6.2.2/spring-aop-6.2.2.jar
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/org/springframework/spring-beans/6.2.2/spring-beans-6.2.2.jar
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/org/springframework/spring-expression/6.2.2/spring-expression-6.2.2.jar
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/io/micrometer/micrometer-observation/1.14.3/micrometer-observation-1.14.3.jar
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/io/micrometer/micrometer-commons/1.14.3/micrometer-commons-1.14.3.jar
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/org/springframework/boot/spring-boot-buildpack-platform/3.4.2/spring-boot-buildpack-platform-3.4.2.jar
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/com/fasterxml/jackson/module/jackson-module-parameter-names/2.18.2/jackson-module-parameter-names-2.18.2.jar
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/org/apache/httpcomponents/client5/httpclient5/5.4.1/httpclient5-5.4.1.jar
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/org/apache/httpcomponents/core5/httpcore5/5.3.1/httpcore5-5.3.1.jar
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/org/apache/httpcomponents/core5/httpcore5-h2/5.3.1/httpcore5-h2-5.3.1.jar
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/org/springframework/boot/spring-boot-loader-tools/3.4.2/spring-boot-loader-tools-3.4.2.jar
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/org/springframework/spring-core/6.2.2/spring-core-6.2.2.jar
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/org/springframework/spring-jcl/6.2.2/spring-jcl-6.2.2.jar
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/org/springframework/spring-context/6.2.2/spring-context-6.2.2.jar
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/org/springframework/spring-aop/6.2.2/spring-aop-6.2.2.jar
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/org/springframework/spring-beans/6.2.2/spring-beans-6.2.2.jar
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/org/springframework/spring-expression/6.2.2/spring-expression-6.2.2.jar
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/io/micrometer/micrometer-observation/1.14.3/micrometer-observation-1.14.3.jar
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/io/micrometer/micrometer-commons/1.14.3/micrometer-commons-1.14.3.jar
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/boot/spring-boot-buildpack-platform/3.4.2/spring-boot-buildpack-platform-3.4.2.jar
Progress (1): 6.7/297 kB
Progress (1): 15/297 kB 
Progress (1): 16/297 kB
Progress (1): 32/297 kB
Progress (1): 33/297 kB
Progress (1): 49/297 kB
Progress (1): 66/297 kB
Progress (1): 82/297 kB
Progress (1): 98/297 kB
Progress (1): 115/297 kB
Progress (1): 131/297 kB
Progress (1): 147/297 kB
Progress (1): 164/297 kB
Progress (1): 180/297 kB
Progress (1): 197/297 kB
Progress (1): 213/297 kB
Progress (1): 229/297 kB
Progress (1): 246/297 kB
Progress (1): 262/297 kB
Progress (1): 279/297 kB
Progress (1): 295/297 kB
Progress (1): 297 kB    
                    
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/boot/spring-boot-buildpack-platform/3.4.2/spring-boot-buildpack-platform-3.4.2.jar (297 kB at 434 kB/s)
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/com/fasterxml/jackson/module/jackson-module-parameter-names/2.18.2/jackson-module-parameter-names-2.18.2.jar
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/apache/httpcomponents/client5/httpclient5/5.4.1/httpclient5-5.4.1.jar
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/apache/httpcomponents/core5/httpcore5/5.3.1/httpcore5-5.3.1.jar
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/apache/httpcomponents/core5/httpcore5-h2/5.3.1/httpcore5-h2-5.3.1.jar
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/boot/spring-boot-loader-tools/3.4.2/spring-boot-loader-tools-3.4.2.jar
Progress (1): 6.7/10 kB
Progress (1): 10 kB    
Progress (2): 10 kB | 6.7/241 kB
Progress (2): 10 kB | 15/241 kB 
Progress (2): 10 kB | 16/241 kB
Progress (2): 10 kB | 32/241 kB
Progress (2): 10 kB | 33/241 kB
Progress (2): 10 kB | 49/241 kB
Progress (2): 10 kB | 66/241 kB
Progress (2): 10 kB | 82/241 kB
Progress (2): 10 kB | 98/241 kB
Progress (2): 10 kB | 115/241 kB
Progress (2): 10 kB | 131/241 kB
Progress (2): 10 kB | 147/241 kB
Progress (2): 10 kB | 164/241 kB
Progress (2): 10 kB | 180/241 kB
Progress (2): 10 kB | 197/241 kB
Progress (2): 10 kB | 213/241 kB
Progress (2): 10 kB | 229/241 kB
Progress (2): 10 kB | 241 kB    
Progress (3): 10 kB | 241 kB | 6.7/465 kB
Progress (3): 10 kB | 241 kB | 15/465 kB 
Progress (3): 10 kB | 241 kB | 31/465 kB
Progress (3): 10 kB | 241 kB | 32/465 kB
Progress (3): 10 kB | 241 kB | 33/465 kB
Progress (4): 10 kB | 241 kB | 33/465 kB | 6.7/906 kB
Progress (4): 10 kB | 241 kB | 33/465 kB | 15/906 kB 
Progress (4): 10 kB | 241 kB | 33/465 kB | 16/906 kB
Progress (4): 10 kB | 241 kB | 33/465 kB | 32/906 kB
Progress (4): 10 kB | 241 kB | 33/465 kB | 33/906 kB
Progress (4): 10 kB | 241 kB | 33/465 kB | 49/906 kB
Progress (4): 10 kB | 241 kB | 33/465 kB | 66/906 kB
Progress (4): 10 kB | 241 kB | 49/465 kB | 66/906 kB
Progress (4): 10 kB | 241 kB | 66/465 kB | 66/906 kB
Progress (5): 10 kB | 241 kB | 66/465 kB | 66/906 kB | 6.7/908 kB
Progress (5): 10 kB | 241 kB | 66/465 kB | 66/906 kB | 15/908 kB 
Progress (5): 10 kB | 241 kB | 66/465 kB | 66/906 kB | 31/908 kB
Progress (5): 10 kB | 241 kB | 66/465 kB | 66/906 kB | 32/908 kB
Progress (5): 10 kB | 241 kB | 66/465 kB | 66/906 kB | 33/908 kB
Progress (5): 10 kB | 241 kB | 66/465 kB | 66/906 kB | 49/908 kB
Progress (5): 10 kB | 241 kB | 82/465 kB | 66/906 kB | 49/908 kB
Progress (5): 10 kB | 241 kB | 98/465 kB | 66/906 kB | 49/908 kB
Progress (5): 10 kB | 241 kB | 98/465 kB | 82/906 kB | 49/908 kB
Progress (5): 10 kB | 241 kB | 98/465 kB | 98/906 kB | 49/908 kB
Progress (5): 10 kB | 241 kB | 98/465 kB | 115/906 kB | 49/908 kB
Progress (5): 10 kB | 241 kB | 98/465 kB | 131/906 kB | 49/908 kB
Progress (5): 10 kB | 241 kB | 98/465 kB | 131/906 kB | 66/908 kB
Progress (5): 10 kB | 241 kB | 98/465 kB | 131/906 kB | 82/908 kB
Progress (5): 10 kB | 241 kB | 98/465 kB | 131/906 kB | 98/908 kB
Progress (5): 10 kB | 241 kB | 115/465 kB | 131/906 kB | 98/908 kB
Progress (5): 10 kB | 241 kB | 131/465 kB | 131/906 kB | 98/908 kB
Progress (5): 10 kB | 241 kB | 131/465 kB | 147/906 kB | 98/908 kB
Progress (5): 10 kB | 241 kB | 131/465 kB | 164/906 kB | 98/908 kB
Progress (5): 10 kB | 241 kB | 131/465 kB | 180/906 kB | 98/908 kB
Progress (5): 10 kB | 241 kB | 131/465 kB | 197/906 kB | 98/908 kB
Progress (5): 10 kB | 241 kB | 131/465 kB | 197/906 kB | 115/908 kB
Progress (5): 10 kB | 241 kB | 131/465 kB | 197/906 kB | 131/908 kB
Progress (5): 10 kB | 241 kB | 131/465 kB | 197/906 kB | 147/908 kB
Progress (5): 10 kB | 241 kB | 147/465 kB | 197/906 kB | 147/908 kB
Progress (5): 10 kB | 241 kB | 164/465 kB | 197/906 kB | 147/908 kB
Progress (5): 10 kB | 241 kB | 164/465 kB | 213/906 kB | 147/908 kB
Progress (5): 10 kB | 241 kB | 164/465 kB | 229/906 kB | 147/908 kB
Progress (5): 10 kB | 241 kB | 164/465 kB | 229/906 kB | 164/908 kB
Progress (5): 10 kB | 241 kB | 164/465 kB | 229/906 kB | 180/908 kB
Progress (5): 10 kB | 241 kB | 164/465 kB | 246/906 kB | 180/908 kB
Progress (5): 10 kB | 241 kB | 164/465 kB | 262/906 kB | 180/908 kB
Progress (5): 10 kB | 241 kB | 164/465 kB | 262/906 kB | 197/908 kB
Progress (5): 10 kB | 241 kB | 164/465 kB | 279/906 kB | 197/908 kB
Progress (5): 10 kB | 241 kB | 180/465 kB | 279/906 kB | 197/908 kB
Progress (5): 10 kB | 241 kB | 197/465 kB | 279/906 kB | 197/908 kB
Progress (5): 10 kB | 241 kB | 213/465 kB | 279/906 kB | 197/908 kB
Progress (5): 10 kB | 241 kB | 213/465 kB | 279/906 kB | 213/908 kB
Progress (5): 10 kB | 241 kB | 213/465 kB | 279/906 kB | 229/908 kB
Progress (5): 10 kB | 241 kB | 213/465 kB | 279/906 kB | 246/908 kB
Progress (5): 10 kB | 241 kB | 213/465 kB | 279/906 kB | 262/908 kB
Progress (5): 10 kB | 241 kB | 229/465 kB | 279/906 kB | 262/908 kB
Progress (5): 10 kB | 241 kB | 246/465 kB | 279/906 kB | 262/908 kB
                                                                   
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/apache/httpcomponents/core5/httpcore5-h2/5.3.1/httpcore5-h2-5.3.1.jar (241 kB at 590 kB/s)
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/spring-core/6.2.2/spring-core-6.2.2.jar
Progress (4): 10 kB | 246/465 kB | 295/906 kB | 262/908 kB
Progress (4): 10 kB | 246/465 kB | 311/906 kB | 262/908 kB
Progress (4): 10 kB | 246/465 kB | 328/906 kB | 262/908 kB
Progress (4): 10 kB | 246/465 kB | 344/906 kB | 262/908 kB
Progress (4): 10 kB | 246/465 kB | 360/906 kB | 262/908 kB
Progress (4): 10 kB | 246/465 kB | 360/906 kB | 279/908 kB
Progress (4): 10 kB | 246/465 kB | 360/906 kB | 295/908 kB
Progress (4): 10 kB | 246/465 kB | 360/906 kB | 311/908 kB
Progress (4): 10 kB | 262/465 kB | 360/906 kB | 311/908 kB
Progress (4): 10 kB | 279/465 kB | 360/906 kB | 311/908 kB
Progress (4): 10 kB | 279/465 kB | 377/906 kB | 311/908 kB
Progress (4): 10 kB | 279/465 kB | 393/906 kB | 311/908 kB
Progress (4): 10 kB | 279/465 kB | 410/906 kB | 311/908 kB
Progress (4): 10 kB | 279/465 kB | 426/906 kB | 311/908 kB
Progress (4): 10 kB | 279/465 kB | 442/906 kB | 311/908 kB
Progress (4): 10 kB | 279/465 kB | 459/906 kB | 311/908 kB
Progress (4): 10 kB | 279/465 kB | 459/906 kB | 328/908 kB
Progress (4): 10 kB | 279/465 kB | 459/906 kB | 344/908 kB
Progress (4): 10 kB | 279/465 kB | 459/906 kB | 360/908 kB
Progress (4): 10 kB | 295/465 kB | 459/906 kB | 360/908 kB
Progress (4): 10 kB | 311/465 kB | 459/906 kB | 360/908 kB
Progress (4): 10 kB | 328/465 kB | 459/906 kB | 360/908 kB
                                                          
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/com/fasterxml/jackson/module/jackson-module-parameter-names/2.18.2/jackson-module-parameter-names-2.18.2.jar (10 kB at 22 kB/s)
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/spring-jcl/6.2.2/spring-jcl-6.2.2.jar
Progress (3): 328/465 kB | 459/906 kB | 377/908 kB
Progress (3): 328/465 kB | 459/906 kB | 393/908 kB
Progress (3): 328/465 kB | 459/906 kB | 410/908 kB
Progress (3): 328/465 kB | 459/906 kB | 426/908 kB
Progress (3): 344/465 kB | 459/906 kB | 426/908 kB
Progress (3): 360/465 kB | 459/906 kB | 426/908 kB
Progress (3): 360/465 kB | 475/906 kB | 426/908 kB
Progress (3): 360/465 kB | 492/906 kB | 426/908 kB
Progress (3): 360/465 kB | 508/906 kB | 426/908 kB
Progress (3): 360/465 kB | 524/906 kB | 426/908 kB
Progress (3): 360/465 kB | 541/906 kB | 426/908 kB
Progress (3): 360/465 kB | 541/906 kB | 442/908 kB
Progress (3): 360/465 kB | 541/906 kB | 459/908 kB
Progress (3): 377/465 kB | 541/906 kB | 459/908 kB
Progress (3): 377/465 kB | 541/906 kB | 475/908 kB
Progress (3): 393/465 kB | 541/906 kB | 475/908 kB
Progress (3): 393/465 kB | 557/906 kB | 475/908 kB
Progress (3): 393/465 kB | 573/906 kB | 475/908 kB
Progress (3): 393/465 kB | 590/906 kB | 475/908 kB
Progress (3): 393/465 kB | 606/906 kB | 475/908 kB
Progress (3): 393/465 kB | 623/906 kB | 475/908 kB
Progress (3): 393/465 kB | 639/906 kB | 475/908 kB
Progress (3): 393/465 kB | 639/906 kB | 492/908 kB
Progress (3): 393/465 kB | 639/906 kB | 508/908 kB
Progress (3): 410/465 kB | 639/906 kB | 508/908 kB
Progress (3): 410/465 kB | 639/906 kB | 524/908 kB
Progress (3): 426/465 kB | 639/906 kB | 524/908 kB
Progress (3): 426/465 kB | 639/906 kB | 541/908 kB
Progress (3): 442/465 kB | 639/906 kB | 541/908 kB
Progress (3): 442/465 kB | 655/906 kB | 541/908 kB
Progress (3): 442/465 kB | 672/906 kB | 541/908 kB
Progress (3): 442/465 kB | 688/906 kB | 541/908 kB
Progress (3): 442/465 kB | 705/906 kB | 541/908 kB
Progress (3): 442/465 kB | 721/906 kB | 541/908 kB
Progress (3): 442/465 kB | 737/906 kB | 541/908 kB
Progress (3): 442/465 kB | 737/906 kB | 557/908 kB
Progress (3): 442/465 kB | 737/906 kB | 573/908 kB
Progress (3): 459/465 kB | 737/906 kB | 573/908 kB
Progress (3): 465 kB | 737/906 kB | 573/908 kB    
Progress (3): 465 kB | 737/906 kB | 590/908 kB
Progress (3): 465 kB | 737/906 kB | 606/908 kB
Progress (3): 465 kB | 737/906 kB | 623/908 kB
Progress (3): 465 kB | 737/906 kB | 639/908 kB
Progress (3): 465 kB | 737/906 kB | 655/908 kB
Progress (3): 465 kB | 754/906 kB | 655/908 kB
Progress (3): 465 kB | 770/906 kB | 655/908 kB
Progress (3): 465 kB | 786/906 kB | 655/908 kB
Progress (3): 465 kB | 803/906 kB | 655/908 kB
Progress (3): 465 kB | 819/906 kB | 655/908 kB
Progress (3): 465 kB | 836/906 kB | 655/908 kB
Progress (3): 465 kB | 836/906 kB | 672/908 kB
Progress (3): 465 kB | 836/906 kB | 688/908 kB
Progress (3): 465 kB | 836/906 kB | 705/908 kB
Progress (3): 465 kB | 852/906 kB | 705/908 kB
Progress (3): 465 kB | 868/906 kB | 705/908 kB
Progress (3): 465 kB | 885/906 kB | 705/908 kB
Progress (3): 465 kB | 901/906 kB | 705/908 kB
Progress (3): 465 kB | 906 kB | 705/908 kB    
Progress (3): 465 kB | 906 kB | 721/908 kB
Progress (3): 465 kB | 906 kB | 737/908 kB
Progress (3): 465 kB | 906 kB | 754/908 kB
Progress (3): 465 kB | 906 kB | 770/908 kB
Progress (3): 465 kB | 906 kB | 786/908 kB
Progress (3): 465 kB | 906 kB | 803/908 kB
Progress (3): 465 kB | 906 kB | 819/908 kB
Progress (3): 465 kB | 906 kB | 836/908 kB
Progress (4): 465 kB | 906 kB | 836/908 kB | 6.7/25 kB
Progress (5): 465 kB | 906 kB | 836/908 kB | 6.7/25 kB | 0/2.0 MB
Progress (5): 465 kB | 906 kB | 836/908 kB | 15/25 kB | 0/2.0 MB 
Progress (5): 465 kB | 906 kB | 836/908 kB | 15/25 kB | 0/2.0 MB
Progress (5): 465 kB | 906 kB | 836/908 kB | 16/25 kB | 0/2.0 MB
Progress (5): 465 kB | 906 kB | 836/908 kB | 16/25 kB | 0/2.0 MB
Progress (5): 465 kB | 906 kB | 836/908 kB | 25 kB | 0/2.0 MB   
Progress (5): 465 kB | 906 kB | 836/908 kB | 25 kB | 0/2.0 MB
Progress (5): 465 kB | 906 kB | 836/908 kB | 25 kB | 0/2.0 MB
Progress (5): 465 kB | 906 kB | 836/908 kB | 25 kB | 0/2.0 MB
Progress (5): 465 kB | 906 kB | 836/908 kB | 25 kB | 0.1/2.0 MB
Progress (5): 465 kB | 906 kB | 836/908 kB | 25 kB | 0.1/2.0 MB
Progress (5): 465 kB | 906 kB | 836/908 kB | 25 kB | 0.1/2.0 MB
Progress (5): 465 kB | 906 kB | 852/908 kB | 25 kB | 0.1/2.0 MB
Progress (5): 465 kB | 906 kB | 868/908 kB | 25 kB | 0.1/2.0 MB
Progress (5): 465 kB | 906 kB | 885/908 kB | 25 kB | 0.1/2.0 MB
Progress (5): 465 kB | 906 kB | 901/908 kB | 25 kB | 0.1/2.0 MB
Progress (5): 465 kB | 906 kB | 901/908 kB | 25 kB | 0.1/2.0 MB
Progress (5): 465 kB | 906 kB | 901/908 kB | 25 kB | 0.1/2.0 MB
Progress (5): 465 kB | 906 kB | 901/908 kB | 25 kB | 0.1/2.0 MB
Progress (5): 465 kB | 906 kB | 901/908 kB | 25 kB | 0.2/2.0 MB
Progress (5): 465 kB | 906 kB | 901/908 kB | 25 kB | 0.2/2.0 MB
Progress (5): 465 kB | 906 kB | 901/908 kB | 25 kB | 0.2/2.0 MB
Progress (5): 465 kB | 906 kB | 901/908 kB | 25 kB | 0.2/2.0 MB
                                                               
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/boot/spring-boot-loader-tools/3.4.2/spring-boot-loader-tools-3.4.2.jar (465 kB at 652 kB/s)
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/spring-context/6.2.2/spring-context-6.2.2.jar
Progress (4): 906 kB | 908 kB | 25 kB | 0.2/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.2/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.2/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.3/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.3/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.3/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.3/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.3/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.3/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.4/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.4/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.4/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.4/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.4/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.4/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.5/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.5/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.5/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.5/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.5/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.5/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.6/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.6/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.6/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.6/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.6/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.6/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.7/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.7/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.7/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.7/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.7/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.7/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.8/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.8/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.8/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.8/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.8/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.8/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.9/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.9/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.9/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.9/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.9/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 0.9/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 1.0/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 1.0/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 1.0/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 1.0/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 1.0/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 1.0/2.0 MB
Progress (4): 906 kB | 908 kB | 25 kB | 1.0/2.0 MB
                                                  
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/apache/httpcomponents/core5/httpcore5/5.3.1/httpcore5-5.3.1.jar (906 kB at 990 kB/s)
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/spring-aop/6.2.2/spring-aop-6.2.2.jar
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/apache/httpcomponents/client5/httpclient5/5.4.1/httpclient5-5.4.1.jar (908 kB at 984 kB/s)
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/spring-beans/6.2.2/spring-beans-6.2.2.jar
Progress (2): 25 kB | 1.1/2.0 MB
Progress (2): 25 kB | 1.1/2.0 MB
Progress (2): 25 kB | 1.1/2.0 MB
Progress (2): 25 kB | 1.1/2.0 MB
Progress (2): 25 kB | 1.1/2.0 MB
Progress (2): 25 kB | 1.1/2.0 MB
Progress (2): 25 kB | 1.2/2.0 MB
                                
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/spring-jcl/6.2.2/spring-jcl-6.2.2.jar (25 kB at 26 kB/s)
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/spring-expression/6.2.2/spring-expression-6.2.2.jar
Progress (1): 1.2/2.0 MB
Progress (2): 1.2/2.0 MB | 0/1.4 MB
Progress (2): 1.2/2.0 MB | 0/1.4 MB
Progress (2): 1.2/2.0 MB | 0/1.4 MB
Progress (2): 1.2/2.0 MB | 0/1.4 MB
Progress (2): 1.2/2.0 MB | 0/1.4 MB
Progress (2): 1.2/2.0 MB | 0/1.4 MB
Progress (2): 1.2/2.0 MB | 0/1.4 MB
Progress (2): 1.2/2.0 MB | 0/1.4 MB
Progress (2): 1.2/2.0 MB | 0/1.4 MB
Progress (2): 1.3/2.0 MB | 0/1.4 MB
Progress (2): 1.3/2.0 MB | 0/1.4 MB
Progress (2): 1.3/2.0 MB | 0/1.4 MB
Progress (2): 1.3/2.0 MB | 0/1.4 MB
Progress (2): 1.3/2.0 MB | 0.1/1.4 MB
Progress (2): 1.3/2.0 MB | 0.1/1.4 MB
Progress (2): 1.3/2.0 MB | 0.1/1.4 MB
Progress (2): 1.3/2.0 MB | 0.1/1.4 MB
Progress (2): 1.3/2.0 MB | 0.1/1.4 MB
Progress (2): 1.4/2.0 MB | 0.1/1.4 MB
Progress (2): 1.4/2.0 MB | 0.1/1.4 MB
Progress (2): 1.4/2.0 MB | 0.1/1.4 MB
Progress (2): 1.4/2.0 MB | 0.1/1.4 MB
Progress (2): 1.4/2.0 MB | 0.1/1.4 MB
Progress (2): 1.4/2.0 MB | 0.1/1.4 MB
Progress (2): 1.4/2.0 MB | 0.1/1.4 MB
Progress (2): 1.4/2.0 MB | 0.1/1.4 MB
Progress (2): 1.5/2.0 MB | 0.1/1.4 MB
Progress (2): 1.5/2.0 MB | 0.1/1.4 MB
Progress (2): 1.5/2.0 MB | 0.1/1.4 MB
Progress (2): 1.5/2.0 MB | 0.1/1.4 MB
Progress (2): 1.5/2.0 MB | 0.1/1.4 MB
Progress (2): 1.5/2.0 MB | 0.1/1.4 MB
Progress (2): 1.5/2.0 MB | 0.1/1.4 MB
Progress (2): 1.5/2.0 MB | 0.1/1.4 MB
Progress (2): 1.6/2.0 MB | 0.1/1.4 MB
Progress (2): 1.6/2.0 MB | 0.1/1.4 MB
Progress (2): 1.6/2.0 MB | 0.2/1.4 MB
Progress (2): 1.6/2.0 MB | 0.2/1.4 MB
Progress (2): 1.6/2.0 MB | 0.2/1.4 MB
Progress (2): 1.6/2.0 MB | 0.2/1.4 MB
Progress (2): 1.6/2.0 MB | 0.2/1.4 MB
Progress (2): 1.7/2.0 MB | 0.2/1.4 MB
Progress (2): 1.7/2.0 MB | 0.2/1.4 MB
Progress (2): 1.7/2.0 MB | 0.2/1.4 MB
Progress (2): 1.7/2.0 MB | 0.2/1.4 MB
Progress (2): 1.7/2.0 MB | 0.2/1.4 MB
Progress (2): 1.7/2.0 MB | 0.2/1.4 MB
Progress (2): 1.7/2.0 MB | 0.2/1.4 MB
Progress (2): 1.7/2.0 MB | 0.2/1.4 MB
Progress (2): 1.7/2.0 MB | 0.2/1.4 MB
Progress (2): 1.8/2.0 MB | 0.2/1.4 MB
Progress (2): 1.8/2.0 MB | 0.2/1.4 MB
Progress (2): 1.8/2.0 MB | 0.2/1.4 MB
Progress (2): 1.8/2.0 MB | 0.2/1.4 MB
Progress (2): 1.8/2.0 MB | 0.2/1.4 MB
Progress (2): 1.8/2.0 MB | 0.2/1.4 MB
Progress (2): 1.8/2.0 MB | 0.2/1.4 MB
Progress (2): 1.8/2.0 MB | 0.3/1.4 MB
Progress (2): 1.8/2.0 MB | 0.3/1.4 MB
Progress (2): 1.9/2.0 MB | 0.3/1.4 MB
Progress (2): 1.9/2.0 MB | 0.3/1.4 MB
Progress (2): 1.9/2.0 MB | 0.3/1.4 MB
Progress (2): 1.9/2.0 MB | 0.3/1.4 MB
Progress (2): 1.9/2.0 MB | 0.3/1.4 MB
Progress (2): 1.9/2.0 MB | 0.3/1.4 MB
Progress (2): 1.9/2.0 MB | 0.3/1.4 MB
Progress (2): 1.9/2.0 MB | 0.3/1.4 MB
Progress (2): 1.9/2.0 MB | 0.3/1.4 MB
Progress (2): 2.0 MB | 0.3/1.4 MB    
Progress (2): 2.0 MB | 0.3/1.4 MB
Progress (2): 2.0 MB | 0.3/1.4 MB
Progress (2): 2.0 MB | 0.3/1.4 MB
Progress (2): 2.0 MB | 0.4/1.4 MB
Progress (3): 2.0 MB | 0.4/1.4 MB | 6.7/418 kB
Progress (3): 2.0 MB | 0.4/1.4 MB | 15/418 kB 
Progress (3): 2.0 MB | 0.4/1.4 MB | 31/418 kB
Progress (3): 2.0 MB | 0.4/1.4 MB | 32/418 kB
Progress (3): 2.0 MB | 0.4/1.4 MB | 49/418 kB
Progress (3): 2.0 MB | 0.4/1.4 MB | 65/418 kB
Progress (3): 2.0 MB | 0.4/1.4 MB | 66/418 kB
Progress (3): 2.0 MB | 0.4/1.4 MB | 82/418 kB
Progress (3): 2.0 MB | 0.4/1.4 MB | 98/418 kB
Progress (3): 2.0 MB | 0.4/1.4 MB | 98/418 kB
Progress (3): 2.0 MB | 0.4/1.4 MB | 98/418 kB
Progress (3): 2.0 MB | 0.4/1.4 MB | 98/418 kB
Progress (4): 2.0 MB | 0.4/1.4 MB | 98/418 kB | 6.7/877 kB
Progress (4): 2.0 MB | 0.4/1.4 MB | 98/418 kB | 15/877 kB 
Progress (4): 2.0 MB | 0.4/1.4 MB | 98/418 kB | 16/877 kB
Progress (4): 2.0 MB | 0.4/1.4 MB | 98/418 kB | 32/877 kB
Progress (4): 2.0 MB | 0.4/1.4 MB | 98/418 kB | 49/877 kB
Progress (4): 2.0 MB | 0.4/1.4 MB | 98/418 kB | 49/877 kB
Progress (4): 2.0 MB | 0.4/1.4 MB | 98/418 kB | 49/877 kB
Progress (4): 2.0 MB | 0.5/1.4 MB | 98/418 kB | 49/877 kB
Progress (4): 2.0 MB | 0.5/1.4 MB | 98/418 kB | 65/877 kB
Progress (4): 2.0 MB | 0.5/1.4 MB | 98/418 kB | 81/877 kB
Progress (4): 2.0 MB | 0.5/1.4 MB | 98/418 kB | 82/877 kB
Progress (4): 2.0 MB | 0.5/1.4 MB | 115/418 kB | 82/877 kB
Progress (4): 2.0 MB | 0.5/1.4 MB | 131/418 kB | 82/877 kB
Progress (4): 2.0 MB | 0.5/1.4 MB | 131/418 kB | 98/877 kB
Progress (4): 2.0 MB | 0.5/1.4 MB | 131/418 kB | 115/877 kB
Progress (4): 2.0 MB | 0.5/1.4 MB | 147/418 kB | 115/877 kB
Progress (4): 2.0 MB | 0.5/1.4 MB | 164/418 kB | 115/877 kB
Progress (4): 2.0 MB | 0.5/1.4 MB | 180/418 kB | 115/877 kB
Progress (4): 2.0 MB | 0.5/1.4 MB | 197/418 kB | 115/877 kB
Progress (4): 2.0 MB | 0.5/1.4 MB | 213/418 kB | 115/877 kB
Progress (4): 2.0 MB | 0.5/1.4 MB | 229/418 kB | 115/877 kB
Progress (4): 2.0 MB | 0.5/1.4 MB | 229/418 kB | 115/877 kB
Progress (4): 2.0 MB | 0.5/1.4 MB | 229/418 kB | 115/877 kB
Progress (4): 2.0 MB | 0.5/1.4 MB | 229/418 kB | 115/877 kB
Progress (4): 2.0 MB | 0.5/1.4 MB | 229/418 kB | 131/877 kB
Progress (4): 2.0 MB | 0.5/1.4 MB | 229/418 kB | 147/877 kB
Progress (4): 2.0 MB | 0.5/1.4 MB | 229/418 kB | 164/877 kB
Progress (4): 2.0 MB | 0.5/1.4 MB | 229/418 kB | 180/877 kB
Progress (5): 2.0 MB | 0.5/1.4 MB | 229/418 kB | 180/877 kB | 6.7/318 kB
Progress (5): 2.0 MB | 0.5/1.4 MB | 229/418 kB | 180/877 kB | 15/318 kB 
Progress (5): 2.0 MB | 0.5/1.4 MB | 229/418 kB | 180/877 kB | 16/318 kB
Progress (5): 2.0 MB | 0.5/1.4 MB | 229/418 kB | 180/877 kB | 32/318 kB
Progress (5): 2.0 MB | 0.5/1.4 MB | 229/418 kB | 180/877 kB | 33/318 kB
Progress (5): 2.0 MB | 0.5/1.4 MB | 246/418 kB | 180/877 kB | 33/318 kB
Progress (5): 2.0 MB | 0.5/1.4 MB | 262/418 kB | 180/877 kB | 33/318 kB
Progress (5): 2.0 MB | 0.5/1.4 MB | 279/418 kB | 180/877 kB | 33/318 kB
Progress (5): 2.0 MB | 0.5/1.4 MB | 295/418 kB | 180/877 kB | 33/318 kB
Progress (5): 2.0 MB | 0.5/1.4 MB | 311/418 kB | 180/877 kB | 33/318 kB
Progress (5): 2.0 MB | 0.5/1.4 MB | 328/418 kB | 180/877 kB | 33/318 kB
Progress (5): 2.0 MB | 0.5/1.4 MB | 344/418 kB | 180/877 kB | 33/318 kB
Progress (5): 2.0 MB | 0.5/1.4 MB | 344/418 kB | 180/877 kB | 33/318 kB
Progress (5): 2.0 MB | 0.5/1.4 MB | 344/418 kB | 180/877 kB | 33/318 kB
Progress (5): 2.0 MB | 0.6/1.4 MB | 344/418 kB | 180/877 kB | 33/318 kB
Progress (5): 2.0 MB | 0.6/1.4 MB | 344/418 kB | 197/877 kB | 33/318 kB
Progress (5): 2.0 MB | 0.6/1.4 MB | 344/418 kB | 213/877 kB | 33/318 kB
Progress (5): 2.0 MB | 0.6/1.4 MB | 344/418 kB | 229/877 kB | 33/318 kB
Progress (5): 2.0 MB | 0.6/1.4 MB | 344/418 kB | 246/877 kB | 33/318 kB
Progress (5): 2.0 MB | 0.6/1.4 MB | 344/418 kB | 246/877 kB | 49/318 kB
Progress (5): 2.0 MB | 0.6/1.4 MB | 344/418 kB | 246/877 kB | 66/318 kB
Progress (5): 2.0 MB | 0.6/1.4 MB | 344/418 kB | 246/877 kB | 82/318 kB
Progress (5): 2.0 MB | 0.6/1.4 MB | 344/418 kB | 246/877 kB | 98/318 kB
                                                                       
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/spring-core/6.2.2/spring-core-6.2.2.jar (2.0 MB at 1.5 MB/s)
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/io/micrometer/micrometer-observation/1.14.3/micrometer-observation-1.14.3.jar
Progress (4): 0.6/1.4 MB | 344/418 kB | 246/877 kB | 98/318 kB
Progress (4): 0.6/1.4 MB | 360/418 kB | 246/877 kB | 98/318 kB
Progress (4): 0.6/1.4 MB | 377/418 kB | 246/877 kB | 98/318 kB
Progress (4): 0.6/1.4 MB | 393/418 kB | 246/877 kB | 98/318 kB
Progress (4): 0.6/1.4 MB | 410/418 kB | 246/877 kB | 98/318 kB
Progress (4): 0.6/1.4 MB | 418 kB | 246/877 kB | 98/318 kB    
Progress (4): 0.6/1.4 MB | 418 kB | 246/877 kB | 98/318 kB
Progress (4): 0.6/1.4 MB | 418 kB | 246/877 kB | 98/318 kB
Progress (4): 0.6/1.4 MB | 418 kB | 262/877 kB | 98/318 kB
Progress (4): 0.6/1.4 MB | 418 kB | 279/877 kB | 98/318 kB
Progress (4): 0.6/1.4 MB | 418 kB | 295/877 kB | 98/318 kB
Progress (4): 0.6/1.4 MB | 418 kB | 311/877 kB | 98/318 kB
Progress (4): 0.6/1.4 MB | 418 kB | 311/877 kB | 115/318 kB
Progress (4): 0.6/1.4 MB | 418 kB | 311/877 kB | 131/318 kB
Progress (4): 0.6/1.4 MB | 418 kB | 311/877 kB | 147/318 kB
Progress (4): 0.6/1.4 MB | 418 kB | 311/877 kB | 147/318 kB
Progress (4): 0.6/1.4 MB | 418 kB | 311/877 kB | 147/318 kB
Progress (4): 0.7/1.4 MB | 418 kB | 311/877 kB | 147/318 kB
Progress (4): 0.7/1.4 MB | 418 kB | 328/877 kB | 147/318 kB
Progress (4): 0.7/1.4 MB | 418 kB | 344/877 kB | 147/318 kB
Progress (4): 0.7/1.4 MB | 418 kB | 360/877 kB | 147/318 kB
Progress (4): 0.7/1.4 MB | 418 kB | 377/877 kB | 147/318 kB
Progress (4): 0.7/1.4 MB | 418 kB | 377/877 kB | 164/318 kB
Progress (4): 0.7/1.4 MB | 418 kB | 377/877 kB | 180/318 kB
Progress (4): 0.7/1.4 MB | 418 kB | 377/877 kB | 197/318 kB
Progress (4): 0.7/1.4 MB | 418 kB | 377/877 kB | 197/318 kB
Progress (4): 0.7/1.4 MB | 418 kB | 377/877 kB | 197/318 kB
Progress (4): 0.7/1.4 MB | 418 kB | 377/877 kB | 197/318 kB
Progress (4): 0.7/1.4 MB | 418 kB | 393/877 kB | 197/318 kB
Progress (4): 0.7/1.4 MB | 418 kB | 410/877 kB | 197/318 kB
Progress (4): 0.7/1.4 MB | 418 kB | 426/877 kB | 197/318 kB
Progress (4): 0.7/1.4 MB | 418 kB | 442/877 kB | 197/318 kB
Progress (4): 0.7/1.4 MB | 418 kB | 442/877 kB | 213/318 kB
Progress (4): 0.7/1.4 MB | 418 kB | 442/877 kB | 229/318 kB
Progress (4): 0.7/1.4 MB | 418 kB | 442/877 kB | 246/318 kB
Progress (4): 0.7/1.4 MB | 418 kB | 442/877 kB | 246/318 kB
Progress (4): 0.7/1.4 MB | 418 kB | 442/877 kB | 246/318 kB
Progress (4): 0.8/1.4 MB | 418 kB | 442/877 kB | 246/318 kB
Progress (4): 0.8/1.4 MB | 418 kB | 459/877 kB | 246/318 kB
Progress (4): 0.8/1.4 MB | 418 kB | 475/877 kB | 246/318 kB
Progress (4): 0.8/1.4 MB | 418 kB | 492/877 kB | 246/318 kB
Progress (4): 0.8/1.4 MB | 418 kB | 508/877 kB | 246/318 kB
Progress (4): 0.8/1.4 MB | 418 kB | 508/877 kB | 262/318 kB
Progress (4): 0.8/1.4 MB | 418 kB | 508/877 kB | 279/318 kB
Progress (4): 0.8/1.4 MB | 418 kB | 508/877 kB | 295/318 kB
Progress (4): 0.8/1.4 MB | 418 kB | 508/877 kB | 295/318 kB
Progress (4): 0.8/1.4 MB | 418 kB | 508/877 kB | 295/318 kB
Progress (4): 0.8/1.4 MB | 418 kB | 508/877 kB | 295/318 kB
Progress (4): 0.8/1.4 MB | 418 kB | 524/877 kB | 295/318 kB
Progress (4): 0.8/1.4 MB | 418 kB | 541/877 kB | 295/318 kB
Progress (4): 0.8/1.4 MB | 418 kB | 557/877 kB | 295/318 kB
Progress (4): 0.8/1.4 MB | 418 kB | 573/877 kB | 295/318 kB
Progress (4): 0.8/1.4 MB | 418 kB | 573/877 kB | 311/318 kB
Progress (4): 0.8/1.4 MB | 418 kB | 573/877 kB | 318 kB    
Progress (4): 0.8/1.4 MB | 418 kB | 573/877 kB | 318 kB
Progress (4): 0.8/1.4 MB | 418 kB | 573/877 kB | 318 kB
Progress (4): 0.9/1.4 MB | 418 kB | 573/877 kB | 318 kB
Progress (4): 0.9/1.4 MB | 418 kB | 573/877 kB | 318 kB
Progress (4): 0.9/1.4 MB | 418 kB | 590/877 kB | 318 kB
Progress (4): 0.9/1.4 MB | 418 kB | 606/877 kB | 318 kB
Progress (4): 0.9/1.4 MB | 418 kB | 623/877 kB | 318 kB
Progress (4): 0.9/1.4 MB | 418 kB | 639/877 kB | 318 kB
Progress (4): 0.9/1.4 MB | 418 kB | 639/877 kB | 318 kB
Progress (4): 0.9/1.4 MB | 418 kB | 639/877 kB | 318 kB
Progress (4): 0.9/1.4 MB | 418 kB | 639/877 kB | 318 kB
Progress (4): 0.9/1.4 MB | 418 kB | 655/877 kB | 318 kB
Progress (4): 0.9/1.4 MB | 418 kB | 672/877 kB | 318 kB
Progress (4): 0.9/1.4 MB | 418 kB | 688/877 kB | 318 kB
Progress (4): 0.9/1.4 MB | 418 kB | 705/877 kB | 318 kB
Progress (4): 0.9/1.4 MB | 418 kB | 721/877 kB | 318 kB
                                                       
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/spring-aop/6.2.2/spring-aop-6.2.2.jar (418 kB at 287 kB/s)
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/io/micrometer/micrometer-commons/1.14.3/micrometer-commons-1.14.3.jar
Progress (3): 0.9/1.4 MB | 721/877 kB | 318 kB
Progress (3): 1.0/1.4 MB | 721/877 kB | 318 kB
Progress (3): 1.0/1.4 MB | 721/877 kB | 318 kB
Progress (3): 1.0/1.4 MB | 737/877 kB | 318 kB
Progress (3): 1.0/1.4 MB | 754/877 kB | 318 kB
Progress (3): 1.0/1.4 MB | 770/877 kB | 318 kB
Progress (3): 1.0/1.4 MB | 786/877 kB | 318 kB
Progress (3): 1.0/1.4 MB | 786/877 kB | 318 kB
Progress (3): 1.0/1.4 MB | 786/877 kB | 318 kB
Progress (3): 1.0/1.4 MB | 786/877 kB | 318 kB
Progress (3): 1.0/1.4 MB | 786/877 kB | 318 kB
Progress (3): 1.0/1.4 MB | 803/877 kB | 318 kB
Progress (3): 1.0/1.4 MB | 819/877 kB | 318 kB
Progress (3): 1.0/1.4 MB | 836/877 kB | 318 kB
Progress (3): 1.0/1.4 MB | 852/877 kB | 318 kB
Progress (4): 1.0/1.4 MB | 852/877 kB | 318 kB | 6.7/75 kB
Progress (4): 1.0/1.4 MB | 852/877 kB | 318 kB | 15/75 kB 
Progress (4): 1.0/1.4 MB | 852/877 kB | 318 kB | 31/75 kB
Progress (4): 1.0/1.4 MB | 852/877 kB | 318 kB | 32/75 kB
Progress (4): 1.0/1.4 MB | 852/877 kB | 318 kB | 33/75 kB
Progress (4): 1.0/1.4 MB | 852/877 kB | 318 kB | 49/75 kB
Progress (4): 1.0/1.4 MB | 852/877 kB | 318 kB | 66/75 kB
Progress (4): 1.0/1.4 MB | 852/877 kB | 318 kB | 75 kB   
Progress (4): 1.0/1.4 MB | 852/877 kB | 318 kB | 75 kB
Progress (4): 1.1/1.4 MB | 852/877 kB | 318 kB | 75 kB
Progress (4): 1.1/1.4 MB | 852/877 kB | 318 kB | 75 kB
Progress (4): 1.1/1.4 MB | 868/877 kB | 318 kB | 75 kB
Progress (4): 1.1/1.4 MB | 877 kB | 318 kB | 75 kB    
Progress (4): 1.1/1.4 MB | 877 kB | 318 kB | 75 kB
Progress (4): 1.1/1.4 MB | 877 kB | 318 kB | 75 kB
Progress (4): 1.1/1.4 MB | 877 kB | 318 kB | 75 kB
Progress (4): 1.1/1.4 MB | 877 kB | 318 kB | 75 kB
                                                  
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/spring-expression/6.2.2/spring-expression-6.2.2.jar (318 kB at 202 kB/s)
Progress (3): 1.2/1.4 MB | 877 kB | 75 kB
Progress (3): 1.2/1.4 MB | 877 kB | 75 kB
Progress (3): 1.2/1.4 MB | 877 kB | 75 kB
Progress (3): 1.2/1.4 MB | 877 kB | 75 kB
Progress (3): 1.2/1.4 MB | 877 kB | 75 kB
Progress (3): 1.2/1.4 MB | 877 kB | 75 kB
Progress (3): 1.3/1.4 MB | 877 kB | 75 kB
Progress (3): 1.3/1.4 MB | 877 kB | 75 kB
Progress (3): 1.3/1.4 MB | 877 kB | 75 kB
Progress (3): 1.3/1.4 MB | 877 kB | 75 kB
Progress (3): 1.3/1.4 MB | 877 kB | 75 kB
                                         
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/io/micrometer/micrometer-observation/1.14.3/micrometer-observation-1.14.3.jar (75 kB at 45 kB/s)
Progress (2): 1.3/1.4 MB | 877 kB
Progress (2): 1.4 MB | 877 kB    
                             
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/spring-beans/6.2.2/spring-beans-6.2.2.jar (877 kB at 528 kB/s)
Progress (2): 1.4 MB | 6.7/48 kB
Progress (2): 1.4 MB | 15/48 kB 
Progress (2): 1.4 MB | 16/48 kB
Progress (2): 1.4 MB | 32/48 kB
Progress (2): 1.4 MB | 33/48 kB
Progress (2): 1.4 MB | 48 kB   
                            
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/spring-context/6.2.2/spring-context-6.2.2.jar (1.4 MB at 716 kB/s)
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/io/micrometer/micrometer-commons/1.14.3/micrometer-commons-1.14.3.jar (48 kB at 25 kB/s)
[INFO] Replacing main artifact /newarch/apps/jenkins/sylp2nj1aue0001/workspace/s-Java_client-sysprin-pipeline-j-2/client-sysprin-writer/target/client-sysprin-writer-0.0.1-SNAPSHOT.jar with repackaged archive, adding nested dependencies in BOOT-INF/.
[INFO] The original artifact has been renamed to /newarch/apps/jenkins/sylp2nj1aue0001/workspace/s-Java_client-sysprin-pipeline-j-2/client-sysprin-writer/target/client-sysprin-writer-0.0.1-SNAPSHOT.jar.original
[INFO] 
[INFO] ---------< trace-client-sysprin-service:client-sysprin-reader >---------
[INFO] Building client-sysprin-reader 0.0.1-SNAPSHOT                      [6/8]
[INFO]   from client-sysprin-reader/pom.xml
[INFO] --------------------------------[ jar ]---------------------------------
[INFO] 
[INFO] --- clean:3.2.0:clean (default-clean) @ client-sysprin-reader ---
[INFO] 
[INFO] --- jacoco:0.8.13:prepare-agent (prepare-agent) @ client-sysprin-reader ---
[INFO] argLine set to -javaagent:/newarch/apps/maven-repo/org/jacoco/org.jacoco.agent/0.8.13/org.jacoco.agent-0.8.13-runtime.jar=destfile=/newarch/apps/jenkins/sylp2nj1aue0001/workspace/s-Java_client-sysprin-pipeline-j-2/client-sysprin-reader/target/jacoco.exec,append=true
[INFO] 
[INFO] --- resources:3.3.1:resources (default-resources) @ client-sysprin-reader ---
[WARNING] Using platform encoding (UTF-8 actually) to copy filtered resources, i.e. build is platform dependent!
[INFO] Copying 1 resource from src/main/resources to target/classes
[INFO] 
[INFO] --- compiler:3.13.0:compile (default-compile) @ client-sysprin-reader ---
[INFO] Recompiling the module because of changed dependency.
[WARNING] File encoding has not been set, using platform encoding UTF-8, i.e. build is platform dependent!
[INFO] Compiling 16 source files with javac [debug parameters release 21] to target/classes
[INFO] 
[INFO] --- resources:3.3.1:testResources (default-testResources) @ client-sysprin-reader ---
[WARNING] Using platform encoding (UTF-8 actually) to copy filtered resources, i.e. build is platform dependent!
[INFO] skip non existing resourceDirectory /newarch/apps/jenkins/sylp2nj1aue0001/workspace/s-Java_client-sysprin-pipeline-j-2/client-sysprin-reader/src/test/resources
[INFO] 
[INFO] --- compiler:3.13.0:testCompile (default-testCompile) @ client-sysprin-reader ---
[INFO] No sources to compile
[INFO] 
[INFO] --- surefire:3.2.5:test (default-test) @ client-sysprin-reader ---
[INFO] No tests to run.
[INFO] 
[INFO] --- jacoco:0.8.13:report (report) @ client-sysprin-reader ---
[INFO] Skipping JaCoCo execution due to missing execution data file.
[INFO] 
[INFO] --- jar:3.4.2:jar (default-jar) @ client-sysprin-reader ---
[INFO] Building jar: /newarch/apps/jenkins/sylp2nj1aue0001/workspace/s-Java_client-sysprin-pipeline-j-2/client-sysprin-reader/target/client-sysprin-reader-0.0.1-SNAPSHOT.jar
[INFO] 
[INFO] --- spring-boot:3.4.2:repackage (default) @ client-sysprin-reader ---
[INFO] Replacing main artifact /newarch/apps/jenkins/sylp2nj1aue0001/workspace/s-Java_client-sysprin-pipeline-j-2/client-sysprin-reader/target/client-sysprin-reader-0.0.1-SNAPSHOT.jar with repackaged archive, adding nested dependencies in BOOT-INF/.
[INFO] The original artifact has been renamed to /newarch/apps/jenkins/sylp2nj1aue0001/workspace/s-Java_client-sysprin-pipeline-j-2/client-sysprin-reader/target/client-sysprin-reader-0.0.1-SNAPSHOT.jar.original
[INFO] 
[INFO] --- jacoco:0.8.13:check (check) @ client-sysprin-reader ---
[INFO] Skipping JaCoCo execution due to missing execution data file:/newarch/apps/jenkins/sylp2nj1aue0001/workspace/s-Java_client-sysprin-pipeline-j-2/client-sysprin-reader/target/jacoco.exec
[INFO] 
[INFO] ----------------< trace-client-sysprin-service:gateway >----------------
[INFO] Building gateway 0.0.1-SNAPSHOT                                    [7/8]
[INFO]   from gateway/pom.xml
[INFO] --------------------------------[ jar ]---------------------------------
Downloading from fiservprotector-maven: https://nexus-ci.onefiserv.net/repository/fiservprotector-maven/org/springframework/cloud/spring-cloud-starter-gateway-server-webmvc/4.3.0/spring-cloud-starter-gateway-server-webmvc-4.3.0.pom
Downloading from simpleapi: https://nexus-ci.onefiserv.net/repository/voltage-maven/org/springframework/cloud/spring-cloud-starter-gateway-server-webmvc/4.3.0/spring-cloud-starter-gateway-server-webmvc-4.3.0.pom
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/org/springframework/cloud/spring-cloud-starter-gateway-server-webmvc/4.3.0/spring-cloud-starter-gateway-server-webmvc-4.3.0.pom
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/org/springframework/cloud/spring-cloud-starter-gateway-server-webmvc/4.3.0/spring-cloud-starter-gateway-server-webmvc-4.3.0.pom
Downloading from vendorsoftwares: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-vendorsoftwares/org/springframework/cloud/spring-cloud-starter-gateway-server-webmvc/4.3.0/spring-cloud-starter-gateway-server-webmvc-4.3.0.pom
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/cloud/spring-cloud-starter-gateway-server-webmvc/4.3.0/spring-cloud-starter-gateway-server-webmvc-4.3.0.pom
Progress (1): 2.7 kB
                    
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/cloud/spring-cloud-starter-gateway-server-webmvc/4.3.0/spring-cloud-starter-gateway-server-webmvc-4.3.0.pom (2.7 kB at 5.7 kB/s)
Downloading from fiservprotector-maven: https://nexus-ci.onefiserv.net/repository/fiservprotector-maven/org/springframework/cloud/spring-cloud-gateway/4.3.0/spring-cloud-gateway-4.3.0.pom
Downloading from simpleapi: https://nexus-ci.onefiserv.net/repository/voltage-maven/org/springframework/cloud/spring-cloud-gateway/4.3.0/spring-cloud-gateway-4.3.0.pom
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/org/springframework/cloud/spring-cloud-gateway/4.3.0/spring-cloud-gateway-4.3.0.pom
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/org/springframework/cloud/spring-cloud-gateway/4.3.0/spring-cloud-gateway-4.3.0.pom
Downloading from vendorsoftwares: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-vendorsoftwares/org/springframework/cloud/spring-cloud-gateway/4.3.0/spring-cloud-gateway-4.3.0.pom
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/cloud/spring-cloud-gateway/4.3.0/spring-cloud-gateway-4.3.0.pom
Progress (1): 2.7 kB
                    
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/cloud/spring-cloud-gateway/4.3.0/spring-cloud-gateway-4.3.0.pom (2.7 kB at 8.4 kB/s)
Downloading from fiservprotector-maven: https://nexus-ci.onefiserv.net/repository/fiservprotector-maven/org/springframework/cloud/spring-cloud-gateway-server-webmvc/4.3.0/spring-cloud-gateway-server-webmvc-4.3.0.pom
Downloading from simpleapi: https://nexus-ci.onefiserv.net/repository/voltage-maven/org/springframework/cloud/spring-cloud-gateway-server-webmvc/4.3.0/spring-cloud-gateway-server-webmvc-4.3.0.pom
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/org/springframework/cloud/spring-cloud-gateway-server-webmvc/4.3.0/spring-cloud-gateway-server-webmvc-4.3.0.pom
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/org/springframework/cloud/spring-cloud-gateway-server-webmvc/4.3.0/spring-cloud-gateway-server-webmvc-4.3.0.pom
Downloading from vendorsoftwares: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-vendorsoftwares/org/springframework/cloud/spring-cloud-gateway-server-webmvc/4.3.0/spring-cloud-gateway-server-webmvc-4.3.0.pom
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/cloud/spring-cloud-gateway-server-webmvc/4.3.0/spring-cloud-gateway-server-webmvc-4.3.0.pom
Progress (1): 2.0 kB
                    
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/cloud/spring-cloud-gateway-server-webmvc/4.3.0/spring-cloud-gateway-server-webmvc-4.3.0.pom (2.0 kB at 4.7 kB/s)
Downloading from fiservprotector-maven: https://nexus-ci.onefiserv.net/repository/fiservprotector-maven/org/springframework/cloud/spring-cloud-gateway-server-mvc/4.3.0/spring-cloud-gateway-server-mvc-4.3.0.pom
Downloading from simpleapi: https://nexus-ci.onefiserv.net/repository/voltage-maven/org/springframework/cloud/spring-cloud-gateway-server-mvc/4.3.0/spring-cloud-gateway-server-mvc-4.3.0.pom
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/org/springframework/cloud/spring-cloud-gateway-server-mvc/4.3.0/spring-cloud-gateway-server-mvc-4.3.0.pom
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/org/springframework/cloud/spring-cloud-gateway-server-mvc/4.3.0/spring-cloud-gateway-server-mvc-4.3.0.pom
Downloading from vendorsoftwares: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-vendorsoftwares/org/springframework/cloud/spring-cloud-gateway-server-mvc/4.3.0/spring-cloud-gateway-server-mvc-4.3.0.pom
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/cloud/spring-cloud-gateway-server-mvc/4.3.0/spring-cloud-gateway-server-mvc-4.3.0.pom
Progress (1): 5.0 kB
                    
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/cloud/spring-cloud-gateway-server-mvc/4.3.0/spring-cloud-gateway-server-mvc-4.3.0.pom (5.0 kB at 12 kB/s)
Downloading from fiservprotector-maven: https://nexus-ci.onefiserv.net/repository/fiservprotector-maven/org/springframework/boot/spring-boot-properties-migrator/3.5.0/spring-boot-properties-migrator-3.5.0.pom
Downloading from simpleapi: https://nexus-ci.onefiserv.net/repository/voltage-maven/org/springframework/boot/spring-boot-properties-migrator/3.5.0/spring-boot-properties-migrator-3.5.0.pom
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/org/springframework/boot/spring-boot-properties-migrator/3.5.0/spring-boot-properties-migrator-3.5.0.pom
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/org/springframework/boot/spring-boot-properties-migrator/3.5.0/spring-boot-properties-migrator-3.5.0.pom
Downloading from vendorsoftwares: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-vendorsoftwares/org/springframework/boot/spring-boot-properties-migrator/3.5.0/spring-boot-properties-migrator-3.5.0.pom
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/boot/spring-boot-properties-migrator/3.5.0/spring-boot-properties-migrator-3.5.0.pom
Progress (1): 2.3 kB
                    
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/boot/spring-boot-properties-migrator/3.5.0/spring-boot-properties-migrator-3.5.0.pom (2.3 kB at 6.1 kB/s)
Downloading from fiservprotector-maven: https://nexus-ci.onefiserv.net/repository/fiservprotector-maven/org/springframework/boot/spring-boot-configuration-metadata/3.5.0/spring-boot-configuration-metadata-3.5.0.pom
Downloading from simpleapi: https://nexus-ci.onefiserv.net/repository/voltage-maven/org/springframework/boot/spring-boot-configuration-metadata/3.5.0/spring-boot-configuration-metadata-3.5.0.pom
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/org/springframework/boot/spring-boot-configuration-metadata/3.5.0/spring-boot-configuration-metadata-3.5.0.pom
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/org/springframework/boot/spring-boot-configuration-metadata/3.5.0/spring-boot-configuration-metadata-3.5.0.pom
Downloading from vendorsoftwares: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-vendorsoftwares/org/springframework/boot/spring-boot-configuration-metadata/3.5.0/spring-boot-configuration-metadata-3.5.0.pom
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/boot/spring-boot-configuration-metadata/3.5.0/spring-boot-configuration-metadata-3.5.0.pom
Progress (1): 2.1 kB
                    
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/boot/spring-boot-configuration-metadata/3.5.0/spring-boot-configuration-metadata-3.5.0.pom (2.1 kB at 5.6 kB/s)
Downloading from fiservprotector-maven: https://nexus-ci.onefiserv.net/repository/fiservprotector-maven/org/springframework/cloud/spring-cloud-starter-gateway-server-webmvc/4.3.0/spring-cloud-starter-gateway-server-webmvc-4.3.0.jar
Downloading from fiservprotector-maven: https://nexus-ci.onefiserv.net/repository/fiservprotector-maven/org/springframework/cloud/spring-cloud-gateway-server-webmvc/4.3.0/spring-cloud-gateway-server-webmvc-4.3.0.jar
Downloading from fiservprotector-maven: https://nexus-ci.onefiserv.net/repository/fiservprotector-maven/org/springframework/cloud/spring-cloud-gateway-server-mvc/4.3.0/spring-cloud-gateway-server-mvc-4.3.0.jar
Downloading from fiservprotector-maven: https://nexus-ci.onefiserv.net/repository/fiservprotector-maven/org/springframework/boot/spring-boot-properties-migrator/3.5.0/spring-boot-properties-migrator-3.5.0.jar
Downloading from fiservprotector-maven: https://nexus-ci.onefiserv.net/repository/fiservprotector-maven/org/springframework/boot/spring-boot-configuration-metadata/3.5.0/spring-boot-configuration-metadata-3.5.0.jar
Downloading from simpleapi: https://nexus-ci.onefiserv.net/repository/voltage-maven/org/springframework/cloud/spring-cloud-starter-gateway-server-webmvc/4.3.0/spring-cloud-starter-gateway-server-webmvc-4.3.0.jar
Downloading from simpleapi: https://nexus-ci.onefiserv.net/repository/voltage-maven/org/springframework/cloud/spring-cloud-gateway-server-webmvc/4.3.0/spring-cloud-gateway-server-webmvc-4.3.0.jar
Downloading from simpleapi: https://nexus-ci.onefiserv.net/repository/voltage-maven/org/springframework/cloud/spring-cloud-gateway-server-mvc/4.3.0/spring-cloud-gateway-server-mvc-4.3.0.jar
Downloading from simpleapi: https://nexus-ci.onefiserv.net/repository/voltage-maven/org/springframework/boot/spring-boot-properties-migrator/3.5.0/spring-boot-properties-migrator-3.5.0.jar
Downloading from simpleapi: https://nexus-ci.onefiserv.net/repository/voltage-maven/org/springframework/boot/spring-boot-configuration-metadata/3.5.0/spring-boot-configuration-metadata-3.5.0.jar
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/org/springframework/cloud/spring-cloud-starter-gateway-server-webmvc/4.3.0/spring-cloud-starter-gateway-server-webmvc-4.3.0.jar
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/org/springframework/cloud/spring-cloud-gateway-server-webmvc/4.3.0/spring-cloud-gateway-server-webmvc-4.3.0.jar
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/org/springframework/cloud/spring-cloud-gateway-server-mvc/4.3.0/spring-cloud-gateway-server-mvc-4.3.0.jar
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/org/springframework/boot/spring-boot-properties-migrator/3.5.0/spring-boot-properties-migrator-3.5.0.jar
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/org/springframework/boot/spring-boot-configuration-metadata/3.5.0/spring-boot-configuration-metadata-3.5.0.jar
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/org/springframework/cloud/spring-cloud-starter-gateway-server-webmvc/4.3.0/spring-cloud-starter-gateway-server-webmvc-4.3.0.jar
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/org/springframework/cloud/spring-cloud-gateway-server-webmvc/4.3.0/spring-cloud-gateway-server-webmvc-4.3.0.jar
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/org/springframework/cloud/spring-cloud-gateway-server-mvc/4.3.0/spring-cloud-gateway-server-mvc-4.3.0.jar
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/org/springframework/boot/spring-boot-properties-migrator/3.5.0/spring-boot-properties-migrator-3.5.0.jar
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/org/springframework/boot/spring-boot-configuration-metadata/3.5.0/spring-boot-configuration-metadata-3.5.0.jar
Downloading from vendorsoftwares: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-vendorsoftwares/org/springframework/cloud/spring-cloud-starter-gateway-server-webmvc/4.3.0/spring-cloud-starter-gateway-server-webmvc-4.3.0.jar
Downloading from vendorsoftwares: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-vendorsoftwares/org/springframework/cloud/spring-cloud-gateway-server-webmvc/4.3.0/spring-cloud-gateway-server-webmvc-4.3.0.jar
Downloading from vendorsoftwares: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-vendorsoftwares/org/springframework/cloud/spring-cloud-gateway-server-mvc/4.3.0/spring-cloud-gateway-server-mvc-4.3.0.jar
Downloading from vendorsoftwares: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-vendorsoftwares/org/springframework/boot/spring-boot-properties-migrator/3.5.0/spring-boot-properties-migrator-3.5.0.jar
Downloading from vendorsoftwares: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-vendorsoftwares/org/springframework/boot/spring-boot-configuration-metadata/3.5.0/spring-boot-configuration-metadata-3.5.0.jar
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/cloud/spring-cloud-starter-gateway-server-webmvc/4.3.0/spring-cloud-starter-gateway-server-webmvc-4.3.0.jar
Progress (1): 2.2 kB
                    
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/cloud/spring-cloud-starter-gateway-server-webmvc/4.3.0/spring-cloud-starter-gateway-server-webmvc-4.3.0.jar (2.2 kB at 5.0 kB/s)
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/cloud/spring-cloud-gateway-server-webmvc/4.3.0/spring-cloud-gateway-server-webmvc-4.3.0.jar
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/cloud/spring-cloud-gateway-server-mvc/4.3.0/spring-cloud-gateway-server-mvc-4.3.0.jar
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/boot/spring-boot-properties-migrator/3.5.0/spring-boot-properties-migrator-3.5.0.jar
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/boot/spring-boot-configuration-metadata/3.5.0/spring-boot-configuration-metadata-3.5.0.jar
Progress (1): 6.7/28 kB
Progress (1): 15/28 kB 
Progress (1): 16/28 kB
Progress (1): 28 kB   
Progress (2): 28 kB | 6.7/22 kB
Progress (2): 28 kB | 15/22 kB 
Progress (2): 28 kB | 22 kB   
Progress (3): 28 kB | 22 kB | 3.4 kB
Progress (4): 28 kB | 22 kB | 3.4 kB | 6.7/328 kB
Progress (4): 28 kB | 22 kB | 3.4 kB | 15/328 kB 
Progress (4): 28 kB | 22 kB | 3.4 kB | 31/328 kB
Progress (4): 28 kB | 22 kB | 3.4 kB | 32/328 kB
Progress (4): 28 kB | 22 kB | 3.4 kB | 49/328 kB
Progress (4): 28 kB | 22 kB | 3.4 kB | 65/328 kB
Progress (4): 28 kB | 22 kB | 3.4 kB | 66/328 kB
Progress (4): 28 kB | 22 kB | 3.4 kB | 82/328 kB
Progress (4): 28 kB | 22 kB | 3.4 kB | 98/328 kB
Progress (4): 28 kB | 22 kB | 3.4 kB | 115/328 kB
Progress (4): 28 kB | 22 kB | 3.4 kB | 131/328 kB
                                                 
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/boot/spring-boot-configuration-metadata/3.5.0/spring-boot-configuration-metadata-3.5.0.jar (28 kB at 82 kB/s)
Progress (3): 22 kB | 3.4 kB | 147/328 kB
Progress (3): 22 kB | 3.4 kB | 164/328 kB
Progress (3): 22 kB | 3.4 kB | 180/328 kB
Progress (3): 22 kB | 3.4 kB | 197/328 kB
Progress (3): 22 kB | 3.4 kB | 213/328 kB
Progress (3): 22 kB | 3.4 kB | 229/328 kB
Progress (3): 22 kB | 3.4 kB | 246/328 kB
Progress (3): 22 kB | 3.4 kB | 262/328 kB
Progress (3): 22 kB | 3.4 kB | 279/328 kB
Progress (3): 22 kB | 3.4 kB | 295/328 kB
Progress (3): 22 kB | 3.4 kB | 311/328 kB
Progress (3): 22 kB | 3.4 kB | 328/328 kB
Progress (3): 22 kB | 3.4 kB | 328 kB    
                                     
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/boot/spring-boot-properties-migrator/3.5.0/spring-boot-properties-migrator-3.5.0.jar (22 kB at 51 kB/s)
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/cloud/spring-cloud-gateway-server-webmvc/4.3.0/spring-cloud-gateway-server-webmvc-4.3.0.jar (3.4 kB at 6.8 kB/s)
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/springframework/cloud/spring-cloud-gateway-server-mvc/4.3.0/spring-cloud-gateway-server-mvc-4.3.0.jar (328 kB at 560 kB/s)
[INFO] 
[INFO] --- clean:3.2.0:clean (default-clean) @ gateway ---
[INFO] 
[INFO] --- resources:3.3.1:resources (default-resources) @ gateway ---
[WARNING] Using platform encoding (UTF-8 actually) to copy filtered resources, i.e. build is platform dependent!
[INFO] Copying 1 resource from src/main/resources to target/classes
[INFO] 
[INFO] --- compiler:3.13.0:compile (default-compile) @ gateway ---
[INFO] Recompiling the module because of changed source code.
[WARNING] File encoding has not been set, using platform encoding UTF-8, i.e. build is platform dependent!
[INFO] Compiling 2 source files with javac [debug parameters release 21] to target/classes
[INFO] 
[INFO] --- resources:3.3.1:testResources (default-testResources) @ gateway ---
[WARNING] Using platform encoding (UTF-8 actually) to copy filtered resources, i.e. build is platform dependent!
[INFO] skip non existing resourceDirectory /newarch/apps/jenkins/sylp2nj1aue0001/workspace/s-Java_client-sysprin-pipeline-j-2/gateway/src/test/resources
[INFO] 
[INFO] --- compiler:3.13.0:testCompile (default-testCompile) @ gateway ---
[INFO] No sources to compile
[INFO] 
[INFO] --- surefire:3.2.5:test (default-test) @ gateway ---
[INFO] No tests to run.
[INFO] 
[INFO] --- jar:3.4.2:jar (default-jar) @ gateway ---
[INFO] Building jar: /newarch/apps/jenkins/sylp2nj1aue0001/workspace/s-Java_client-sysprin-pipeline-j-2/gateway/target/gateway-0.0.1-SNAPSHOT.jar
[INFO] 
[INFO] --- spring-boot:3.4.2:repackage (default) @ gateway ---
[INFO] Replacing main artifact /newarch/apps/jenkins/sylp2nj1aue0001/workspace/s-Java_client-sysprin-pipeline-j-2/gateway/target/gateway-0.0.1-SNAPSHOT.jar with repackaged archive, adding nested dependencies in BOOT-INF/.
[INFO] The original artifact has been renamed to /newarch/apps/jenkins/sylp2nj1aue0001/workspace/s-Java_client-sysprin-pipeline-j-2/gateway/target/gateway-0.0.1-SNAPSHOT.jar.original
[INFO] 
[INFO] ----------< trace-client-sysprin-service:search-integration >-----------
[INFO] Building search-integration 0.0.1-SNAPSHOT                         [8/8]
[INFO]   from search-integration/pom.xml
[INFO] --------------------------------[ jar ]---------------------------------
Downloading from fiservprotector-maven: https://nexus-ci.onefiserv.net/repository/fiservprotector-maven/com/github/ben-manes/caffeine/caffeine/3.2.0/caffeine-3.2.0.pom
Downloading from simpleapi: https://nexus-ci.onefiserv.net/repository/voltage-maven/com/github/ben-manes/caffeine/caffeine/3.2.0/caffeine-3.2.0.pom
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/com/github/ben-manes/caffeine/caffeine/3.2.0/caffeine-3.2.0.pom
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/com/github/ben-manes/caffeine/caffeine/3.2.0/caffeine-3.2.0.pom
Downloading from vendorsoftwares: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-vendorsoftwares/com/github/ben-manes/caffeine/caffeine/3.2.0/caffeine-3.2.0.pom
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/com/github/ben-manes/caffeine/caffeine/3.2.0/caffeine-3.2.0.pom
Progress (1): 2.1 kB
                    
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/com/github/ben-manes/caffeine/caffeine/3.2.0/caffeine-3.2.0.pom (2.1 kB at 5.4 kB/s)
Downloading from fiservprotector-maven: https://nexus-ci.onefiserv.net/repository/fiservprotector-maven/org/apache/lucene/lucene-core/8.11.2/lucene-core-8.11.2.pom
Downloading from simpleapi: https://nexus-ci.onefiserv.net/repository/voltage-maven/org/apache/lucene/lucene-core/8.11.2/lucene-core-8.11.2.pom
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/org/apache/lucene/lucene-core/8.11.2/lucene-core-8.11.2.pom
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/org/apache/lucene/lucene-core/8.11.2/lucene-core-8.11.2.pom
Downloading from vendorsoftwares: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-vendorsoftwares/org/apache/lucene/lucene-core/8.11.2/lucene-core-8.11.2.pom
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/apache/lucene/lucene-core/8.11.2/lucene-core-8.11.2.pom
Progress (1): 1.8 kB
                    
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/apache/lucene/lucene-core/8.11.2/lucene-core-8.11.2.pom (1.8 kB at 4.1 kB/s)
Downloading from fiservprotector-maven: https://nexus-ci.onefiserv.net/repository/fiservprotector-maven/org/apache/lucene/lucene-parent/8.11.2/lucene-parent-8.11.2.pom
Downloading from simpleapi: https://nexus-ci.onefiserv.net/repository/voltage-maven/org/apache/lucene/lucene-parent/8.11.2/lucene-parent-8.11.2.pom
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/org/apache/lucene/lucene-parent/8.11.2/lucene-parent-8.11.2.pom
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/org/apache/lucene/lucene-parent/8.11.2/lucene-parent-8.11.2.pom
Downloading from vendorsoftwares: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-vendorsoftwares/org/apache/lucene/lucene-parent/8.11.2/lucene-parent-8.11.2.pom
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/apache/lucene/lucene-parent/8.11.2/lucene-parent-8.11.2.pom
Progress (1): 2.5 kB
                    
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/apache/lucene/lucene-parent/8.11.2/lucene-parent-8.11.2.pom (2.5 kB at 7.4 kB/s)
Downloading from fiservprotector-maven: https://nexus-ci.onefiserv.net/repository/fiservprotector-maven/org/apache/lucene/lucene-solr-grandparent/8.11.2/lucene-solr-grandparent-8.11.2.pom
Downloading from simpleapi: https://nexus-ci.onefiserv.net/repository/voltage-maven/org/apache/lucene/lucene-solr-grandparent/8.11.2/lucene-solr-grandparent-8.11.2.pom
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/org/apache/lucene/lucene-solr-grandparent/8.11.2/lucene-solr-grandparent-8.11.2.pom
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/org/apache/lucene/lucene-solr-grandparent/8.11.2/lucene-solr-grandparent-8.11.2.pom
Downloading from vendorsoftwares: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-vendorsoftwares/org/apache/lucene/lucene-solr-grandparent/8.11.2/lucene-solr-grandparent-8.11.2.pom
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/apache/lucene/lucene-solr-grandparent/8.11.2/lucene-solr-grandparent-8.11.2.pom
Progress (1): 6.7/505 kB
Progress (1): 15/505 kB 
Progress (1): 31/505 kB
Progress (1): 32/505 kB
Progress (1): 33/505 kB
Progress (1): 49/505 kB
Progress (1): 66/505 kB
Progress (1): 82/505 kB
Progress (1): 98/505 kB
Progress (1): 115/505 kB
Progress (1): 131/505 kB
Progress (1): 147/505 kB
Progress (1): 164/505 kB
Progress (1): 180/505 kB
Progress (1): 197/505 kB
Progress (1): 213/505 kB
Progress (1): 229/505 kB
Progress (1): 246/505 kB
Progress (1): 262/505 kB
Progress (1): 279/505 kB
Progress (1): 295/505 kB
Progress (1): 311/505 kB
Progress (1): 328/505 kB
Progress (1): 344/505 kB
Progress (1): 360/505 kB
Progress (1): 377/505 kB
Progress (1): 393/505 kB
Progress (1): 410/505 kB
Progress (1): 426/505 kB
Progress (1): 442/505 kB
Progress (1): 459/505 kB
Progress (1): 475/505 kB
Progress (1): 492/505 kB
Progress (1): 505 kB    
                    
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/apache/lucene/lucene-solr-grandparent/8.11.2/lucene-solr-grandparent-8.11.2.pom (505 kB at 884 kB/s)
Downloading from fiservprotector-maven: https://nexus-ci.onefiserv.net/repository/fiservprotector-maven/org/apache/lucene/lucene-analyzers-common/8.11.2/lucene-analyzers-common-8.11.2.pom
Downloading from simpleapi: https://nexus-ci.onefiserv.net/repository/voltage-maven/org/apache/lucene/lucene-analyzers-common/8.11.2/lucene-analyzers-common-8.11.2.pom
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/org/apache/lucene/lucene-analyzers-common/8.11.2/lucene-analyzers-common-8.11.2.pom
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/org/apache/lucene/lucene-analyzers-common/8.11.2/lucene-analyzers-common-8.11.2.pom
Downloading from vendorsoftwares: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-vendorsoftwares/org/apache/lucene/lucene-analyzers-common/8.11.2/lucene-analyzers-common-8.11.2.pom
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/apache/lucene/lucene-analyzers-common/8.11.2/lucene-analyzers-common-8.11.2.pom
Progress (1): 1.9 kB
                    
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/apache/lucene/lucene-analyzers-common/8.11.2/lucene-analyzers-common-8.11.2.pom (1.9 kB at 4.4 kB/s)
Downloading from fiservprotector-maven: https://nexus-ci.onefiserv.net/repository/fiservprotector-maven/org/apache/lucene/lucene-queryparser/8.11.2/lucene-queryparser-8.11.2.pom
Downloading from simpleapi: https://nexus-ci.onefiserv.net/repository/voltage-maven/org/apache/lucene/lucene-queryparser/8.11.2/lucene-queryparser-8.11.2.pom
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/org/apache/lucene/lucene-queryparser/8.11.2/lucene-queryparser-8.11.2.pom
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/org/apache/lucene/lucene-queryparser/8.11.2/lucene-queryparser-8.11.2.pom
Downloading from vendorsoftwares: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-vendorsoftwares/org/apache/lucene/lucene-queryparser/8.11.2/lucene-queryparser-8.11.2.pom
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/apache/lucene/lucene-queryparser/8.11.2/lucene-queryparser-8.11.2.pom
Progress (1): 2.2 kB
                    
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/apache/lucene/lucene-queryparser/8.11.2/lucene-queryparser-8.11.2.pom (2.2 kB at 5.2 kB/s)
Downloading from fiservprotector-maven: https://nexus-ci.onefiserv.net/repository/fiservprotector-maven/org/apache/lucene/lucene-queries/8.11.2/lucene-queries-8.11.2.pom
Downloading from simpleapi: https://nexus-ci.onefiserv.net/repository/voltage-maven/org/apache/lucene/lucene-queries/8.11.2/lucene-queries-8.11.2.pom
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/org/apache/lucene/lucene-queries/8.11.2/lucene-queries-8.11.2.pom
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/org/apache/lucene/lucene-queries/8.11.2/lucene-queries-8.11.2.pom
Downloading from vendorsoftwares: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-vendorsoftwares/org/apache/lucene/lucene-queries/8.11.2/lucene-queries-8.11.2.pom
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/apache/lucene/lucene-queries/8.11.2/lucene-queries-8.11.2.pom
Progress (1): 1.9 kB
                    
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/apache/lucene/lucene-queries/8.11.2/lucene-queries-8.11.2.pom (1.9 kB at 4.3 kB/s)
Downloading from fiservprotector-maven: https://nexus-ci.onefiserv.net/repository/fiservprotector-maven/org/apache/lucene/lucene-sandbox/8.11.2/lucene-sandbox-8.11.2.pom
Downloading from simpleapi: https://nexus-ci.onefiserv.net/repository/voltage-maven/org/apache/lucene/lucene-sandbox/8.11.2/lucene-sandbox-8.11.2.pom
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/org/apache/lucene/lucene-sandbox/8.11.2/lucene-sandbox-8.11.2.pom
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/org/apache/lucene/lucene-sandbox/8.11.2/lucene-sandbox-8.11.2.pom
Downloading from vendorsoftwares: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-vendorsoftwares/org/apache/lucene/lucene-sandbox/8.11.2/lucene-sandbox-8.11.2.pom
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/apache/lucene/lucene-sandbox/8.11.2/lucene-sandbox-8.11.2.pom
Progress (1): 1.9 kB
                    
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/apache/lucene/lucene-sandbox/8.11.2/lucene-sandbox-8.11.2.pom (1.9 kB at 4.3 kB/s)
Downloading from fiservprotector-maven: https://nexus-ci.onefiserv.net/repository/fiservprotector-maven/com/github/ben-manes/caffeine/caffeine/3.2.0/caffeine-3.2.0.jar
Downloading from fiservprotector-maven: https://nexus-ci.onefiserv.net/repository/fiservprotector-maven/org/apache/lucene/lucene-core/8.11.2/lucene-core-8.11.2.jar
Downloading from fiservprotector-maven: https://nexus-ci.onefiserv.net/repository/fiservprotector-maven/org/apache/lucene/lucene-analyzers-common/8.11.2/lucene-analyzers-common-8.11.2.jar
Downloading from fiservprotector-maven: https://nexus-ci.onefiserv.net/repository/fiservprotector-maven/org/apache/lucene/lucene-queryparser/8.11.2/lucene-queryparser-8.11.2.jar
Downloading from fiservprotector-maven: https://nexus-ci.onefiserv.net/repository/fiservprotector-maven/org/apache/lucene/lucene-queries/8.11.2/lucene-queries-8.11.2.jar
Downloading from fiservprotector-maven: https://nexus-ci.onefiserv.net/repository/fiservprotector-maven/org/apache/lucene/lucene-sandbox/8.11.2/lucene-sandbox-8.11.2.jar
Downloading from simpleapi: https://nexus-ci.onefiserv.net/repository/voltage-maven/com/github/ben-manes/caffeine/caffeine/3.2.0/caffeine-3.2.0.jar
Downloading from simpleapi: https://nexus-ci.onefiserv.net/repository/voltage-maven/org/apache/lucene/lucene-core/8.11.2/lucene-core-8.11.2.jar
Downloading from simpleapi: https://nexus-ci.onefiserv.net/repository/voltage-maven/org/apache/lucene/lucene-analyzers-common/8.11.2/lucene-analyzers-common-8.11.2.jar
Downloading from simpleapi: https://nexus-ci.onefiserv.net/repository/voltage-maven/org/apache/lucene/lucene-queryparser/8.11.2/lucene-queryparser-8.11.2.jar
Downloading from simpleapi: https://nexus-ci.onefiserv.net/repository/voltage-maven/org/apache/lucene/lucene-queries/8.11.2/lucene-queries-8.11.2.jar
Downloading from simpleapi: https://nexus-ci.onefiserv.net/repository/voltage-maven/org/apache/lucene/lucene-sandbox/8.11.2/lucene-sandbox-8.11.2.jar
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/com/github/ben-manes/caffeine/caffeine/3.2.0/caffeine-3.2.0.jar
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/org/apache/lucene/lucene-core/8.11.2/lucene-core-8.11.2.jar
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/org/apache/lucene/lucene-analyzers-common/8.11.2/lucene-analyzers-common-8.11.2.jar
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/org/apache/lucene/lucene-queryparser/8.11.2/lucene-queryparser-8.11.2.jar
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/org/apache/lucene/lucene-queries/8.11.2/lucene-queries-8.11.2.jar
Downloading from nexus-ci-proxy: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-proxy-nexusappdev-releases/org/apache/lucene/lucene-sandbox/8.11.2/lucene-sandbox-8.11.2.jar
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/com/github/ben-manes/caffeine/caffeine/3.2.0/caffeine-3.2.0.jar
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/org/apache/lucene/lucene-core/8.11.2/lucene-core-8.11.2.jar
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/org/apache/lucene/lucene-analyzers-common/8.11.2/lucene-analyzers-common-8.11.2.jar
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/org/apache/lucene/lucene-queryparser/8.11.2/lucene-queryparser-8.11.2.jar
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/org/apache/lucene/lucene-queries/8.11.2/lucene-queries-8.11.2.jar
Downloading from nexus-ci-releases: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases/org/apache/lucene/lucene-sandbox/8.11.2/lucene-sandbox-8.11.2.jar
Downloading from vendorsoftwares: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-vendorsoftwares/com/github/ben-manes/caffeine/caffeine/3.2.0/caffeine-3.2.0.jar
Downloading from vendorsoftwares: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-vendorsoftwares/org/apache/lucene/lucene-core/8.11.2/lucene-core-8.11.2.jar
Downloading from vendorsoftwares: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-vendorsoftwares/org/apache/lucene/lucene-analyzers-common/8.11.2/lucene-analyzers-common-8.11.2.jar
Downloading from vendorsoftwares: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-vendorsoftwares/org/apache/lucene/lucene-queryparser/8.11.2/lucene-queryparser-8.11.2.jar
Downloading from vendorsoftwares: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-vendorsoftwares/org/apache/lucene/lucene-queries/8.11.2/lucene-queries-8.11.2.jar
Downloading from vendorsoftwares: https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-vendorsoftwares/org/apache/lucene/lucene-sandbox/8.11.2/lucene-sandbox-8.11.2.jar
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/com/github/ben-manes/caffeine/caffeine/3.2.0/caffeine-3.2.0.jar
Progress (1): 6.7/907 kB
Progress (1): 15/907 kB 
Progress (1): 16/907 kB
Progress (1): 32/907 kB
Progress (1): 49/907 kB
Progress (1): 65/907 kB
Progress (1): 66/907 kB
Progress (1): 82/907 kB
Progress (1): 98/907 kB
Progress (1): 115/907 kB
Progress (1): 131/907 kB
Progress (1): 147/907 kB
Progress (1): 164/907 kB
Progress (1): 180/907 kB
Progress (1): 197/907 kB
Progress (1): 213/907 kB
Progress (1): 229/907 kB
Progress (1): 246/907 kB
Progress (1): 262/907 kB
Progress (1): 279/907 kB
Progress (1): 295/907 kB
Progress (1): 311/907 kB
Progress (1): 328/907 kB
Progress (1): 344/907 kB
Progress (1): 360/907 kB
Progress (1): 377/907 kB
Progress (1): 393/907 kB
Progress (1): 410/907 kB
Progress (1): 426/907 kB
Progress (1): 442/907 kB
Progress (1): 459/907 kB
Progress (1): 475/907 kB
Progress (1): 492/907 kB
Progress (1): 508/907 kB
Progress (1): 524/907 kB
Progress (1): 541/907 kB
Progress (1): 557/907 kB
Progress (1): 573/907 kB
Progress (1): 590/907 kB
Progress (1): 606/907 kB
Progress (1): 623/907 kB
Progress (1): 639/907 kB
Progress (1): 655/907 kB
Progress (1): 672/907 kB
Progress (1): 688/907 kB
Progress (1): 705/907 kB
Progress (1): 721/907 kB
Progress (1): 737/907 kB
Progress (1): 754/907 kB
Progress (1): 770/907 kB
Progress (1): 786/907 kB
Progress (1): 803/907 kB
Progress (1): 819/907 kB
Progress (1): 836/907 kB
Progress (1): 852/907 kB
Progress (1): 868/907 kB
Progress (1): 885/907 kB
Progress (1): 901/907 kB
Progress (1): 907 kB    
                    
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/com/github/ben-manes/caffeine/caffeine/3.2.0/caffeine-3.2.0.jar (907 kB at 1.5 MB/s)
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/apache/lucene/lucene-core/8.11.2/lucene-core-8.11.2.jar
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/apache/lucene/lucene-analyzers-common/8.11.2/lucene-analyzers-common-8.11.2.jar
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/apache/lucene/lucene-queryparser/8.11.2/lucene-queryparser-8.11.2.jar
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/apache/lucene/lucene-queries/8.11.2/lucene-queries-8.11.2.jar
Downloading from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/apache/lucene/lucene-sandbox/8.11.2/lucene-sandbox-8.11.2.jar
Progress (1): 0/1.8 MB
Progress (1): 0/1.8 MB
Progress (1): 0/1.8 MB
Progress (1): 0/1.8 MB
Progress (1): 0/1.8 MB
Progress (1): 0/1.8 MB
Progress (2): 0/1.8 MB | 6.7/383 kB
Progress (2): 0/1.8 MB | 15/383 kB 
Progress (2): 0/1.8 MB | 31/383 kB
Progress (2): 0/1.8 MB | 32/383 kB
Progress (2): 0/1.8 MB | 49/383 kB
Progress (2): 0/1.8 MB | 65/383 kB
Progress (2): 0/1.8 MB | 66/383 kB
Progress (2): 0/1.8 MB | 82/383 kB
Progress (2): 0/1.8 MB | 98/383 kB
Progress (2): 0/1.8 MB | 115/383 kB
Progress (2): 0/1.8 MB | 131/383 kB
Progress (2): 0/1.8 MB | 147/383 kB
Progress (2): 0/1.8 MB | 164/383 kB
Progress (3): 0/1.8 MB | 164/383 kB | 0/3.6 MB
Progress (3): 0/1.8 MB | 164/383 kB | 0/3.6 MB
Progress (3): 0/1.8 MB | 164/383 kB | 0/3.6 MB
Progress (3): 0/1.8 MB | 164/383 kB | 0/3.6 MB
Progress (3): 0/1.8 MB | 164/383 kB | 0/3.6 MB
Progress (3): 0/1.8 MB | 164/383 kB | 0.1/3.6 MB
Progress (3): 0/1.8 MB | 164/383 kB | 0.1/3.6 MB
Progress (3): 0/1.8 MB | 164/383 kB | 0.1/3.6 MB
Progress (3): 0/1.8 MB | 164/383 kB | 0.1/3.6 MB
Progress (3): 0/1.8 MB | 164/383 kB | 0.1/3.6 MB
Progress (4): 0/1.8 MB | 164/383 kB | 0.1/3.6 MB | 6.7/382 kB
Progress (4): 0/1.8 MB | 164/383 kB | 0.1/3.6 MB | 15/382 kB 
Progress (4): 0/1.8 MB | 164/383 kB | 0.1/3.6 MB | 16/382 kB
Progress (4): 0/1.8 MB | 164/383 kB | 0.1/3.6 MB | 32/382 kB
Progress (4): 0/1.8 MB | 164/383 kB | 0.1/3.6 MB | 49/382 kB
Progress (4): 0.1/1.8 MB | 164/383 kB | 0.1/3.6 MB | 49/382 kB
Progress (4): 0.1/1.8 MB | 164/383 kB | 0.1/3.6 MB | 65/382 kB
Progress (4): 0.1/1.8 MB | 164/383 kB | 0.1/3.6 MB | 66/382 kB
Progress (4): 0.1/1.8 MB | 164/383 kB | 0.1/3.6 MB | 66/382 kB
Progress (4): 0.1/1.8 MB | 164/383 kB | 0.1/3.6 MB | 66/382 kB
Progress (4): 0.1/1.8 MB | 164/383 kB | 0.1/3.6 MB | 66/382 kB
Progress (4): 0.1/1.8 MB | 164/383 kB | 0.1/3.6 MB | 66/382 kB
Progress (4): 0.1/1.8 MB | 164/383 kB | 0.1/3.6 MB | 66/382 kB
Progress (4): 0.1/1.8 MB | 164/383 kB | 0.2/3.6 MB | 66/382 kB
Progress (4): 0.1/1.8 MB | 164/383 kB | 0.2/3.6 MB | 66/382 kB
Progress (4): 0.1/1.8 MB | 164/383 kB | 0.2/3.6 MB | 66/382 kB
Progress (4): 0.1/1.8 MB | 164/383 kB | 0.2/3.6 MB | 66/382 kB
Progress (4): 0.1/1.8 MB | 164/383 kB | 0.2/3.6 MB | 66/382 kB
Progress (4): 0.1/1.8 MB | 164/383 kB | 0.2/3.6 MB | 66/382 kB
Progress (4): 0.1/1.8 MB | 180/383 kB | 0.2/3.6 MB | 66/382 kB
Progress (4): 0.1/1.8 MB | 197/383 kB | 0.2/3.6 MB | 66/382 kB
Progress (4): 0.1/1.8 MB | 213/383 kB | 0.2/3.6 MB | 66/382 kB
Progress (4): 0.1/1.8 MB | 229/383 kB | 0.2/3.6 MB | 66/382 kB
Progress (4): 0.1/1.8 MB | 246/383 kB | 0.2/3.6 MB | 66/382 kB
Progress (4): 0.1/1.8 MB | 262/383 kB | 0.2/3.6 MB | 66/382 kB
Progress (4): 0.1/1.8 MB | 279/383 kB | 0.2/3.6 MB | 66/382 kB
Progress (4): 0.1/1.8 MB | 295/383 kB | 0.2/3.6 MB | 66/382 kB
Progress (4): 0.1/1.8 MB | 311/383 kB | 0.2/3.6 MB | 66/382 kB
Progress (4): 0.1/1.8 MB | 328/383 kB | 0.2/3.6 MB | 66/382 kB
Progress (4): 0.1/1.8 MB | 344/383 kB | 0.2/3.6 MB | 66/382 kB
Progress (4): 0.1/1.8 MB | 344/383 kB | 0.2/3.6 MB | 82/382 kB
Progress (4): 0.1/1.8 MB | 344/383 kB | 0.2/3.6 MB | 82/382 kB
Progress (4): 0.1/1.8 MB | 344/383 kB | 0.2/3.6 MB | 98/382 kB
Progress (4): 0.1/1.8 MB | 344/383 kB | 0.2/3.6 MB | 115/382 kB
Progress (4): 0.1/1.8 MB | 344/383 kB | 0.2/3.6 MB | 131/382 kB
Progress (4): 0.1/1.8 MB | 344/383 kB | 0.2/3.6 MB | 131/382 kB
Progress (4): 0.2/1.8 MB | 344/383 kB | 0.2/3.6 MB | 131/382 kB
Progress (4): 0.2/1.8 MB | 344/383 kB | 0.2/3.6 MB | 131/382 kB
Progress (4): 0.2/1.8 MB | 344/383 kB | 0.3/3.6 MB | 131/382 kB
Progress (4): 0.2/1.8 MB | 344/383 kB | 0.3/3.6 MB | 131/382 kB
Progress (4): 0.2/1.8 MB | 344/383 kB | 0.3/3.6 MB | 131/382 kB
Progress (4): 0.2/1.8 MB | 344/383 kB | 0.3/3.6 MB | 131/382 kB
Progress (4): 0.2/1.8 MB | 344/383 kB | 0.3/3.6 MB | 131/382 kB
Progress (4): 0.2/1.8 MB | 344/383 kB | 0.3/3.6 MB | 131/382 kB
Progress (4): 0.2/1.8 MB | 344/383 kB | 0.4/3.6 MB | 131/382 kB
Progress (4): 0.2/1.8 MB | 344/383 kB | 0.4/3.6 MB | 131/382 kB
Progress (4): 0.2/1.8 MB | 344/383 kB | 0.4/3.6 MB | 131/382 kB
Progress (5): 0.2/1.8 MB | 344/383 kB | 0.4/3.6 MB | 131/382 kB | 6.7/245 kB
Progress (5): 0.2/1.8 MB | 344/383 kB | 0.4/3.6 MB | 131/382 kB | 15/245 kB 
Progress (5): 0.2/1.8 MB | 344/383 kB | 0.4/3.6 MB | 131/382 kB | 31/245 kB
Progress (5): 0.2/1.8 MB | 344/383 kB | 0.4/3.6 MB | 131/382 kB | 32/245 kB
Progress (5): 0.2/1.8 MB | 344/383 kB | 0.4/3.6 MB | 131/382 kB | 33/245 kB
Progress (5): 0.2/1.8 MB | 344/383 kB | 0.4/3.6 MB | 147/382 kB | 33/245 kB
Progress (5): 0.2/1.8 MB | 344/383 kB | 0.4/3.6 MB | 147/382 kB | 49/245 kB
Progress (5): 0.2/1.8 MB | 344/383 kB | 0.4/3.6 MB | 164/382 kB | 49/245 kB
Progress (5): 0.2/1.8 MB | 344/383 kB | 0.4/3.6 MB | 164/382 kB | 49/245 kB
Progress (5): 0.2/1.8 MB | 344/383 kB | 0.4/3.6 MB | 180/382 kB | 49/245 kB
Progress (5): 0.2/1.8 MB | 344/383 kB | 0.4/3.6 MB | 180/382 kB | 49/245 kB
Progress (5): 0.2/1.8 MB | 344/383 kB | 0.4/3.6 MB | 197/382 kB | 49/245 kB
Progress (5): 0.2/1.8 MB | 344/383 kB | 0.4/3.6 MB | 213/382 kB | 49/245 kB
Progress (5): 0.2/1.8 MB | 344/383 kB | 0.4/3.6 MB | 213/382 kB | 49/245 kB
Progress (5): 0.2/1.8 MB | 360/383 kB | 0.4/3.6 MB | 213/382 kB | 49/245 kB
Progress (5): 0.2/1.8 MB | 377/383 kB | 0.4/3.6 MB | 213/382 kB | 49/245 kB
Progress (5): 0.2/1.8 MB | 383 kB | 0.4/3.6 MB | 213/382 kB | 49/245 kB    
Progress (5): 0.2/1.8 MB | 383 kB | 0.4/3.6 MB | 213/382 kB | 49/245 kB
Progress (5): 0.2/1.8 MB | 383 kB | 0.4/3.6 MB | 213/382 kB | 49/245 kB
Progress (5): 0.2/1.8 MB | 383 kB | 0.4/3.6 MB | 213/382 kB | 49/245 kB
Progress (5): 0.2/1.8 MB | 383 kB | 0.5/3.6 MB | 213/382 kB | 49/245 kB
Progress (5): 0.2/1.8 MB | 383 kB | 0.5/3.6 MB | 213/382 kB | 49/245 kB
Progress (5): 0.2/1.8 MB | 383 kB | 0.5/3.6 MB | 213/382 kB | 49/245 kB
Progress (5): 0.2/1.8 MB | 383 kB | 0.5/3.6 MB | 213/382 kB | 49/245 kB
Progress (5): 0.2/1.8 MB | 383 kB | 0.5/3.6 MB | 213/382 kB | 49/245 kB
Progress (5): 0.2/1.8 MB | 383 kB | 0.5/3.6 MB | 213/382 kB | 66/245 kB
Progress (5): 0.2/1.8 MB | 383 kB | 0.5/3.6 MB | 213/382 kB | 66/245 kB
Progress (5): 0.2/1.8 MB | 383 kB | 0.5/3.6 MB | 213/382 kB | 82/245 kB
Progress (5): 0.2/1.8 MB | 383 kB | 0.5/3.6 MB | 213/382 kB | 98/245 kB
Progress (5): 0.2/1.8 MB | 383 kB | 0.5/3.6 MB | 229/382 kB | 98/245 kB
Progress (5): 0.3/1.8 MB | 383 kB | 0.5/3.6 MB | 229/382 kB | 98/245 kB
Progress (5): 0.3/1.8 MB | 383 kB | 0.5/3.6 MB | 246/382 kB | 98/245 kB
Progress (5): 0.3/1.8 MB | 383 kB | 0.5/3.6 MB | 246/382 kB | 98/245 kB
Progress (5): 0.3/1.8 MB | 383 kB | 0.5/3.6 MB | 262/382 kB | 98/245 kB
Progress (5): 0.3/1.8 MB | 383 kB | 0.5/3.6 MB | 262/382 kB | 98/245 kB
Progress (5): 0.3/1.8 MB | 383 kB | 0.5/3.6 MB | 279/382 kB | 98/245 kB
Progress (5): 0.3/1.8 MB | 383 kB | 0.5/3.6 MB | 279/382 kB | 98/245 kB
Progress (5): 0.3/1.8 MB | 383 kB | 0.6/3.6 MB | 279/382 kB | 98/245 kB
Progress (5): 0.3/1.8 MB | 383 kB | 0.6/3.6 MB | 279/382 kB | 98/245 kB
Progress (5): 0.3/1.8 MB | 383 kB | 0.6/3.6 MB | 279/382 kB | 98/245 kB
Progress (5): 0.3/1.8 MB | 383 kB | 0.6/3.6 MB | 279/382 kB | 98/245 kB
Progress (5): 0.3/1.8 MB | 383 kB | 0.6/3.6 MB | 279/382 kB | 98/245 kB
Progress (5): 0.3/1.8 MB | 383 kB | 0.6/3.6 MB | 279/382 kB | 98/245 kB
Progress (5): 0.3/1.8 MB | 383 kB | 0.7/3.6 MB | 279/382 kB | 98/245 kB
Progress (5): 0.3/1.8 MB | 383 kB | 0.7/3.6 MB | 279/382 kB | 115/245 kB
Progress (5): 0.3/1.8 MB | 383 kB | 0.7/3.6 MB | 279/382 kB | 115/245 kB
Progress (5): 0.3/1.8 MB | 383 kB | 0.7/3.6 MB | 279/382 kB | 131/245 kB
Progress (5): 0.3/1.8 MB | 383 kB | 0.7/3.6 MB | 279/382 kB | 147/245 kB
Progress (5): 0.3/1.8 MB | 383 kB | 0.7/3.6 MB | 295/382 kB | 147/245 kB
Progress (5): 0.3/1.8 MB | 383 kB | 0.7/3.6 MB | 311/382 kB | 147/245 kB
Progress (5): 0.3/1.8 MB | 383 kB | 0.7/3.6 MB | 311/382 kB | 147/245 kB
Progress (5): 0.3/1.8 MB | 383 kB | 0.7/3.6 MB | 311/382 kB | 147/245 kB
Progress (5): 0.4/1.8 MB | 383 kB | 0.7/3.6 MB | 311/382 kB | 147/245 kB
Progress (5): 0.4/1.8 MB | 383 kB | 0.7/3.6 MB | 328/382 kB | 147/245 kB
Progress (5): 0.4/1.8 MB | 383 kB | 0.7/3.6 MB | 344/382 kB | 147/245 kB
Progress (5): 0.4/1.8 MB | 383 kB | 0.7/3.6 MB | 360/382 kB | 147/245 kB
Progress (5): 0.4/1.8 MB | 383 kB | 0.7/3.6 MB | 360/382 kB | 147/245 kB
Progress (5): 0.4/1.8 MB | 383 kB | 0.7/3.6 MB | 360/382 kB | 147/245 kB
Progress (5): 0.4/1.8 MB | 383 kB | 0.7/3.6 MB | 360/382 kB | 147/245 kB
Progress (5): 0.4/1.8 MB | 383 kB | 0.7/3.6 MB | 360/382 kB | 147/245 kB
Progress (5): 0.4/1.8 MB | 383 kB | 0.7/3.6 MB | 360/382 kB | 147/245 kB
Progress (5): 0.4/1.8 MB | 383 kB | 0.8/3.6 MB | 360/382 kB | 147/245 kB
Progress (5): 0.4/1.8 MB | 383 kB | 0.8/3.6 MB | 360/382 kB | 147/245 kB
Progress (5): 0.4/1.8 MB | 383 kB | 0.8/3.6 MB | 360/382 kB | 147/245 kB
Progress (5): 0.4/1.8 MB | 383 kB | 0.8/3.6 MB | 360/382 kB | 147/245 kB
Progress (5): 0.4/1.8 MB | 383 kB | 0.8/3.6 MB | 360/382 kB | 164/245 kB
Progress (5): 0.4/1.8 MB | 383 kB | 0.8/3.6 MB | 360/382 kB | 180/245 kB
Progress (5): 0.4/1.8 MB | 383 kB | 0.8/3.6 MB | 360/382 kB | 197/245 kB
Progress (5): 0.4/1.8 MB | 383 kB | 0.8/3.6 MB | 360/382 kB | 213/245 kB
Progress (5): 0.4/1.8 MB | 383 kB | 0.8/3.6 MB | 377/382 kB | 213/245 kB
Progress (5): 0.4/1.8 MB | 383 kB | 0.8/3.6 MB | 382 kB | 213/245 kB    
Progress (5): 0.4/1.8 MB | 383 kB | 0.8/3.6 MB | 382 kB | 213/245 kB
Progress (5): 0.4/1.8 MB | 383 kB | 0.8/3.6 MB | 382 kB | 213/245 kB
Progress (5): 0.4/1.8 MB | 383 kB | 0.8/3.6 MB | 382 kB | 213/245 kB
Progress (5): 0.4/1.8 MB | 383 kB | 0.8/3.6 MB | 382 kB | 213/245 kB
Progress (5): 0.4/1.8 MB | 383 kB | 0.8/3.6 MB | 382 kB | 213/245 kB
Progress (5): 0.4/1.8 MB | 383 kB | 0.8/3.6 MB | 382 kB | 213/245 kB
Progress (5): 0.4/1.8 MB | 383 kB | 0.9/3.6 MB | 382 kB | 213/245 kB
Progress (5): 0.4/1.8 MB | 383 kB | 0.9/3.6 MB | 382 kB | 213/245 kB
Progress (5): 0.4/1.8 MB | 383 kB | 0.9/3.6 MB | 382 kB | 213/245 kB
Progress (5): 0.4/1.8 MB | 383 kB | 0.9/3.6 MB | 382 kB | 213/245 kB
Progress (5): 0.4/1.8 MB | 383 kB | 0.9/3.6 MB | 382 kB | 213/245 kB
Progress (5): 0.4/1.8 MB | 383 kB | 0.9/3.6 MB | 382 kB | 213/245 kB
Progress (5): 0.4/1.8 MB | 383 kB | 0.9/3.6 MB | 382 kB | 229/245 kB
Progress (5): 0.4/1.8 MB | 383 kB | 0.9/3.6 MB | 382 kB | 245 kB    
Progress (5): 0.5/1.8 MB | 383 kB | 0.9/3.6 MB | 382 kB | 245 kB
Progress (5): 0.5/1.8 MB | 383 kB | 0.9/3.6 MB | 382 kB | 245 kB
Progress (5): 0.5/1.8 MB | 383 kB | 0.9/3.6 MB | 382 kB | 245 kB
Progress (5): 0.5/1.8 MB | 383 kB | 0.9/3.6 MB | 382 kB | 245 kB
Progress (5): 0.5/1.8 MB | 383 kB | 1.0/3.6 MB | 382 kB | 245 kB
Progress (5): 0.5/1.8 MB | 383 kB | 1.0/3.6 MB | 382 kB | 245 kB
Progress (5): 0.5/1.8 MB | 383 kB | 1.0/3.6 MB | 382 kB | 245 kB
Progress (5): 0.5/1.8 MB | 383 kB | 1.0/3.6 MB | 382 kB | 245 kB
Progress (5): 0.5/1.8 MB | 383 kB | 1.0/3.6 MB | 382 kB | 245 kB
Progress (5): 0.5/1.8 MB | 383 kB | 1.0/3.6 MB | 382 kB | 245 kB
Progress (5): 0.5/1.8 MB | 383 kB | 1.0/3.6 MB | 382 kB | 245 kB
Progress (5): 0.5/1.8 MB | 383 kB | 1.0/3.6 MB | 382 kB | 245 kB
Progress (5): 0.5/1.8 MB | 383 kB | 1.0/3.6 MB | 382 kB | 245 kB
Progress (5): 0.5/1.8 MB | 383 kB | 1.0/3.6 MB | 382 kB | 245 kB
Progress (5): 0.6/1.8 MB | 383 kB | 1.0/3.6 MB | 382 kB | 245 kB
Progress (5): 0.6/1.8 MB | 383 kB | 1.1/3.6 MB | 382 kB | 245 kB
Progress (5): 0.6/1.8 MB | 383 kB | 1.1/3.6 MB | 382 kB | 245 kB
Progress (5): 0.6/1.8 MB | 383 kB | 1.1/3.6 MB | 382 kB | 245 kB
Progress (5): 0.6/1.8 MB | 383 kB | 1.1/3.6 MB | 382 kB | 245 kB
Progress (5): 0.6/1.8 MB | 383 kB | 1.1/3.6 MB | 382 kB | 245 kB
Progress (5): 0.6/1.8 MB | 383 kB | 1.1/3.6 MB | 382 kB | 245 kB
Progress (5): 0.6/1.8 MB | 383 kB | 1.2/3.6 MB | 382 kB | 245 kB
Progress (5): 0.6/1.8 MB | 383 kB | 1.2/3.6 MB | 382 kB | 245 kB
Progress (5): 0.6/1.8 MB | 383 kB | 1.2/3.6 MB | 382 kB | 245 kB
Progress (5): 0.6/1.8 MB | 383 kB | 1.2/3.6 MB | 382 kB | 245 kB
Progress (5): 0.6/1.8 MB | 383 kB | 1.2/3.6 MB | 382 kB | 245 kB
Progress (5): 0.6/1.8 MB | 383 kB | 1.2/3.6 MB | 382 kB | 245 kB
Progress (5): 0.6/1.8 MB | 383 kB | 1.2/3.6 MB | 382 kB | 245 kB
Progress (5): 0.6/1.8 MB | 383 kB | 1.2/3.6 MB | 382 kB | 245 kB
Progress (5): 0.6/1.8 MB | 383 kB | 1.2/3.6 MB | 382 kB | 245 kB
Progress (5): 0.6/1.8 MB | 383 kB | 1.2/3.6 MB | 382 kB | 245 kB
Progress (5): 0.6/1.8 MB | 383 kB | 1.3/3.6 MB | 382 kB | 245 kB
Progress (5): 0.6/1.8 MB | 383 kB | 1.3/3.6 MB | 382 kB | 245 kB
Progress (5): 0.6/1.8 MB | 383 kB | 1.3/3.6 MB | 382 kB | 245 kB
Progress (5): 0.6/1.8 MB | 383 kB | 1.3/3.6 MB | 382 kB | 245 kB
Progress (5): 0.6/1.8 MB | 383 kB | 1.3/3.6 MB | 382 kB | 245 kB
                                                                
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/apache/lucene/lucene-queryparser/8.11.2/lucene-queryparser-8.11.2.jar (383 kB at 762 kB/s)
Progress (4): 0.6/1.8 MB | 1.3/3.6 MB | 382 kB | 245 kB
Progress (4): 0.7/1.8 MB | 1.3/3.6 MB | 382 kB | 245 kB
Progress (4): 0.7/1.8 MB | 1.3/3.6 MB | 382 kB | 245 kB
Progress (4): 0.7/1.8 MB | 1.3/3.6 MB | 382 kB | 245 kB
Progress (4): 0.7/1.8 MB | 1.3/3.6 MB | 382 kB | 245 kB
Progress (4): 0.7/1.8 MB | 1.4/3.6 MB | 382 kB | 245 kB
Progress (4): 0.7/1.8 MB | 1.4/3.6 MB | 382 kB | 245 kB
Progress (4): 0.7/1.8 MB | 1.4/3.6 MB | 382 kB | 245 kB
Progress (4): 0.7/1.8 MB | 1.4/3.6 MB | 382 kB | 245 kB
Progress (4): 0.7/1.8 MB | 1.4/3.6 MB | 382 kB | 245 kB
Progress (4): 0.7/1.8 MB | 1.4/3.6 MB | 382 kB | 245 kB
Progress (4): 0.7/1.8 MB | 1.5/3.6 MB | 382 kB | 245 kB
Progress (4): 0.7/1.8 MB | 1.5/3.6 MB | 382 kB | 245 kB
Progress (4): 0.7/1.8 MB | 1.5/3.6 MB | 382 kB | 245 kB
Progress (4): 0.7/1.8 MB | 1.5/3.6 MB | 382 kB | 245 kB
Progress (4): 0.7/1.8 MB | 1.5/3.6 MB | 382 kB | 245 kB
Progress (4): 0.8/1.8 MB | 1.5/3.6 MB | 382 kB | 245 kB
Progress (4): 0.8/1.8 MB | 1.5/3.6 MB | 382 kB | 245 kB
Progress (4): 0.8/1.8 MB | 1.5/3.6 MB | 382 kB | 245 kB
Progress (4): 0.8/1.8 MB | 1.5/3.6 MB | 382 kB | 245 kB
Progress (4): 0.8/1.8 MB | 1.5/3.6 MB | 382 kB | 245 kB
Progress (4): 0.8/1.8 MB | 1.6/3.6 MB | 382 kB | 245 kB
Progress (4): 0.8/1.8 MB | 1.6/3.6 MB | 382 kB | 245 kB
Progress (4): 0.8/1.8 MB | 1.6/3.6 MB | 382 kB | 245 kB
Progress (4): 0.8/1.8 MB | 1.6/3.6 MB | 382 kB | 245 kB
Progress (4): 0.8/1.8 MB | 1.6/3.6 MB | 382 kB | 245 kB
Progress (4): 0.8/1.8 MB | 1.6/3.6 MB | 382 kB | 245 kB
Progress (4): 0.8/1.8 MB | 1.6/3.6 MB | 382 kB | 245 kB
Progress (4): 0.8/1.8 MB | 1.6/3.6 MB | 382 kB | 245 kB
Progress (4): 0.8/1.8 MB | 1.6/3.6 MB | 382 kB | 245 kB
Progress (4): 0.8/1.8 MB | 1.6/3.6 MB | 382 kB | 245 kB
Progress (4): 0.8/1.8 MB | 1.6/3.6 MB | 382 kB | 245 kB
Progress (4): 0.8/1.8 MB | 1.7/3.6 MB | 382 kB | 245 kB
Progress (4): 0.8/1.8 MB | 1.7/3.6 MB | 382 kB | 245 kB
Progress (4): 0.8/1.8 MB | 1.7/3.6 MB | 382 kB | 245 kB
Progress (4): 0.8/1.8 MB | 1.7/3.6 MB | 382 kB | 245 kB
Progress (4): 0.8/1.8 MB | 1.7/3.6 MB | 382 kB | 245 kB
Progress (4): 0.8/1.8 MB | 1.7/3.6 MB | 382 kB | 245 kB
                                                       
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/apache/lucene/lucene-queries/8.11.2/lucene-queries-8.11.2.jar (382 kB at 655 kB/s)
Progress (3): 0.9/1.8 MB | 1.7/3.6 MB | 245 kB
Progress (3): 0.9/1.8 MB | 1.7/3.6 MB | 245 kB
Progress (3): 0.9/1.8 MB | 1.7/3.6 MB | 245 kB
Progress (3): 0.9/1.8 MB | 1.7/3.6 MB | 245 kB
Progress (3): 0.9/1.8 MB | 1.8/3.6 MB | 245 kB
Progress (3): 0.9/1.8 MB | 1.8/3.6 MB | 245 kB
Progress (3): 0.9/1.8 MB | 1.8/3.6 MB | 245 kB
Progress (3): 0.9/1.8 MB | 1.8/3.6 MB | 245 kB
Progress (3): 0.9/1.8 MB | 1.8/3.6 MB | 245 kB
Progress (3): 0.9/1.8 MB | 1.8/3.6 MB | 245 kB
Progress (3): 0.9/1.8 MB | 1.9/3.6 MB | 245 kB
Progress (3): 0.9/1.8 MB | 1.9/3.6 MB | 245 kB
Progress (3): 0.9/1.8 MB | 1.9/3.6 MB | 245 kB
Progress (3): 0.9/1.8 MB | 1.9/3.6 MB | 245 kB
Progress (3): 0.9/1.8 MB | 1.9/3.6 MB | 245 kB
Progress (3): 1.0/1.8 MB | 1.9/3.6 MB | 245 kB
Progress (3): 1.0/1.8 MB | 1.9/3.6 MB | 245 kB
Progress (3): 1.0/1.8 MB | 1.9/3.6 MB | 245 kB
Progress (3): 1.0/1.8 MB | 1.9/3.6 MB | 245 kB
Progress (3): 1.0/1.8 MB | 1.9/3.6 MB | 245 kB
Progress (3): 1.0/1.8 MB | 1.9/3.6 MB | 245 kB
Progress (3): 1.0/1.8 MB | 2.0/3.6 MB | 245 kB
Progress (3): 1.0/1.8 MB | 2.0/3.6 MB | 245 kB
Progress (3): 1.0/1.8 MB | 2.0/3.6 MB | 245 kB
Progress (3): 1.0/1.8 MB | 2.0/3.6 MB | 245 kB
Progress (3): 1.0/1.8 MB | 2.0/3.6 MB | 245 kB
Progress (3): 1.0/1.8 MB | 2.0/3.6 MB | 245 kB
Progress (3): 1.0/1.8 MB | 2.0/3.6 MB | 245 kB
Progress (3): 1.0/1.8 MB | 2.0/3.6 MB | 245 kB
                                              
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/apache/lucene/lucene-sandbox/8.11.2/lucene-sandbox-8.11.2.jar (245 kB at 375 kB/s)
Progress (2): 1.0/1.8 MB | 2.0/3.6 MB
Progress (2): 1.0/1.8 MB | 2.0/3.6 MB
Progress (2): 1.0/1.8 MB | 2.1/3.6 MB
Progress (2): 1.0/1.8 MB | 2.1/3.6 MB
Progress (2): 1.0/1.8 MB | 2.1/3.6 MB
Progress (2): 1.0/1.8 MB | 2.1/3.6 MB
Progress (2): 1.0/1.8 MB | 2.1/3.6 MB
Progress (2): 1.0/1.8 MB | 2.1/3.6 MB
Progress (2): 1.0/1.8 MB | 2.2/3.6 MB
Progress (2): 1.0/1.8 MB | 2.2/3.6 MB
Progress (2): 1.1/1.8 MB | 2.2/3.6 MB
Progress (2): 1.1/1.8 MB | 2.2/3.6 MB
Progress (2): 1.1/1.8 MB | 2.2/3.6 MB
Progress (2): 1.1/1.8 MB | 2.2/3.6 MB
Progress (2): 1.1/1.8 MB | 2.2/3.6 MB
Progress (2): 1.1/1.8 MB | 2.2/3.6 MB
Progress (2): 1.1/1.8 MB | 2.2/3.6 MB
Progress (2): 1.1/1.8 MB | 2.2/3.6 MB
Progress (2): 1.1/1.8 MB | 2.2/3.6 MB
Progress (2): 1.1/1.8 MB | 2.3/3.6 MB
Progress (2): 1.1/1.8 MB | 2.3/3.6 MB
Progress (2): 1.1/1.8 MB | 2.3/3.6 MB
Progress (2): 1.1/1.8 MB | 2.3/3.6 MB
Progress (2): 1.1/1.8 MB | 2.3/3.6 MB
Progress (2): 1.1/1.8 MB | 2.3/3.6 MB
Progress (2): 1.2/1.8 MB | 2.3/3.6 MB
Progress (2): 1.2/1.8 MB | 2.3/3.6 MB
Progress (2): 1.2/1.8 MB | 2.3/3.6 MB
Progress (2): 1.2/1.8 MB | 2.3/3.6 MB
Progress (2): 1.2/1.8 MB | 2.4/3.6 MB
Progress (2): 1.2/1.8 MB | 2.4/3.6 MB
Progress (2): 1.2/1.8 MB | 2.4/3.6 MB
Progress (2): 1.2/1.8 MB | 2.4/3.6 MB
Progress (2): 1.2/1.8 MB | 2.4/3.6 MB
Progress (2): 1.2/1.8 MB | 2.4/3.6 MB
Progress (2): 1.2/1.8 MB | 2.4/3.6 MB
Progress (2): 1.2/1.8 MB | 2.4/3.6 MB
Progress (2): 1.2/1.8 MB | 2.4/3.6 MB
Progress (2): 1.2/1.8 MB | 2.4/3.6 MB
Progress (2): 1.2/1.8 MB | 2.5/3.6 MB
Progress (2): 1.2/1.8 MB | 2.5/3.6 MB
Progress (2): 1.2/1.8 MB | 2.5/3.6 MB
Progress (2): 1.2/1.8 MB | 2.5/3.6 MB
Progress (2): 1.2/1.8 MB | 2.5/3.6 MB
Progress (2): 1.2/1.8 MB | 2.5/3.6 MB
Progress (2): 1.2/1.8 MB | 2.6/3.6 MB
Progress (2): 1.2/1.8 MB | 2.6/3.6 MB
Progress (2): 1.2/1.8 MB | 2.6/3.6 MB
Progress (2): 1.3/1.8 MB | 2.6/3.6 MB
Progress (2): 1.3/1.8 MB | 2.6/3.6 MB
Progress (2): 1.3/1.8 MB | 2.6/3.6 MB
Progress (2): 1.3/1.8 MB | 2.6/3.6 MB
Progress (2): 1.3/1.8 MB | 2.6/3.6 MB
Progress (2): 1.3/1.8 MB | 2.6/3.6 MB
Progress (2): 1.3/1.8 MB | 2.6/3.6 MB
Progress (2): 1.3/1.8 MB | 2.6/3.6 MB
Progress (2): 1.3/1.8 MB | 2.7/3.6 MB
Progress (2): 1.3/1.8 MB | 2.7/3.6 MB
Progress (2): 1.3/1.8 MB | 2.7/3.6 MB
Progress (2): 1.3/1.8 MB | 2.7/3.6 MB
Progress (2): 1.3/1.8 MB | 2.7/3.6 MB
Progress (2): 1.3/1.8 MB | 2.7/3.6 MB
Progress (2): 1.3/1.8 MB | 2.7/3.6 MB
Progress (2): 1.4/1.8 MB | 2.7/3.6 MB
Progress (2): 1.4/1.8 MB | 2.7/3.6 MB
Progress (2): 1.4/1.8 MB | 2.7/3.6 MB
Progress (2): 1.4/1.8 MB | 2.8/3.6 MB
Progress (2): 1.4/1.8 MB | 2.8/3.6 MB
Progress (2): 1.4/1.8 MB | 2.8/3.6 MB
Progress (2): 1.4/1.8 MB | 2.8/3.6 MB
Progress (2): 1.4/1.8 MB | 2.8/3.6 MB
Progress (2): 1.4/1.8 MB | 2.8/3.6 MB
Progress (2): 1.4/1.8 MB | 2.9/3.6 MB
Progress (2): 1.4/1.8 MB | 2.9/3.6 MB
Progress (2): 1.4/1.8 MB | 2.9/3.6 MB
Progress (2): 1.4/1.8 MB | 2.9/3.6 MB
Progress (2): 1.4/1.8 MB | 2.9/3.6 MB
Progress (2): 1.5/1.8 MB | 2.9/3.6 MB
Progress (2): 1.5/1.8 MB | 2.9/3.6 MB
Progress (2): 1.5/1.8 MB | 2.9/3.6 MB
Progress (2): 1.5/1.8 MB | 2.9/3.6 MB
Progress (2): 1.5/1.8 MB | 2.9/3.6 MB
Progress (2): 1.5/1.8 MB | 2.9/3.6 MB
Progress (2): 1.5/1.8 MB | 2.9/3.6 MB
Progress (2): 1.5/1.8 MB | 3.0/3.6 MB
Progress (2): 1.5/1.8 MB | 3.0/3.6 MB
Progress (2): 1.5/1.8 MB | 3.0/3.6 MB
Progress (2): 1.5/1.8 MB | 3.0/3.6 MB
Progress (2): 1.5/1.8 MB | 3.0/3.6 MB
Progress (2): 1.5/1.8 MB | 3.0/3.6 MB
Progress (2): 1.5/1.8 MB | 3.0/3.6 MB
Progress (2): 1.5/1.8 MB | 3.0/3.6 MB
Progress (2): 1.5/1.8 MB | 3.0/3.6 MB
Progress (2): 1.5/1.8 MB | 3.0/3.6 MB
Progress (2): 1.5/1.8 MB | 3.1/3.6 MB
Progress (2): 1.5/1.8 MB | 3.1/3.6 MB
Progress (2): 1.5/1.8 MB | 3.1/3.6 MB
Progress (2): 1.5/1.8 MB | 3.1/3.6 MB
Progress (2): 1.5/1.8 MB | 3.1/3.6 MB
Progress (2): 1.5/1.8 MB | 3.1/3.6 MB
Progress (2): 1.5/1.8 MB | 3.2/3.6 MB
Progress (2): 1.6/1.8 MB | 3.2/3.6 MB
Progress (2): 1.6/1.8 MB | 3.2/3.6 MB
Progress (2): 1.6/1.8 MB | 3.2/3.6 MB
Progress (2): 1.6/1.8 MB | 3.2/3.6 MB
Progress (2): 1.6/1.8 MB | 3.2/3.6 MB
Progress (2): 1.6/1.8 MB | 3.2/3.6 MB
Progress (2): 1.6/1.8 MB | 3.2/3.6 MB
Progress (2): 1.6/1.8 MB | 3.2/3.6 MB
Progress (2): 1.6/1.8 MB | 3.2/3.6 MB
Progress (2): 1.6/1.8 MB | 3.2/3.6 MB
Progress (2): 1.6/1.8 MB | 3.3/3.6 MB
Progress (2): 1.6/1.8 MB | 3.3/3.6 MB
Progress (2): 1.6/1.8 MB | 3.3/3.6 MB
Progress (2): 1.6/1.8 MB | 3.3/3.6 MB
Progress (2): 1.6/1.8 MB | 3.3/3.6 MB
Progress (2): 1.7/1.8 MB | 3.3/3.6 MB
Progress (2): 1.7/1.8 MB | 3.3/3.6 MB
Progress (2): 1.7/1.8 MB | 3.3/3.6 MB
Progress (2): 1.7/1.8 MB | 3.3/3.6 MB
Progress (2): 1.7/1.8 MB | 3.3/3.6 MB
Progress (2): 1.7/1.8 MB | 3.3/3.6 MB
Progress (2): 1.7/1.8 MB | 3.4/3.6 MB
Progress (2): 1.7/1.8 MB | 3.4/3.6 MB
Progress (2): 1.7/1.8 MB | 3.4/3.6 MB
Progress (2): 1.7/1.8 MB | 3.4/3.6 MB
Progress (2): 1.7/1.8 MB | 3.4/3.6 MB
Progress (2): 1.7/1.8 MB | 3.4/3.6 MB
Progress (2): 1.7/1.8 MB | 3.5/3.6 MB
Progress (2): 1.7/1.8 MB | 3.5/3.6 MB
Progress (2): 1.7/1.8 MB | 3.5/3.6 MB
Progress (2): 1.8/1.8 MB | 3.5/3.6 MB
Progress (2): 1.8/1.8 MB | 3.5/3.6 MB
Progress (2): 1.8/1.8 MB | 3.5/3.6 MB
Progress (2): 1.8/1.8 MB | 3.5/3.6 MB
Progress (2): 1.8/1.8 MB | 3.5/3.6 MB
Progress (2): 1.8/1.8 MB | 3.5/3.6 MB
Progress (2): 1.8/1.8 MB | 3.5/3.6 MB
Progress (2): 1.8/1.8 MB | 3.6/3.6 MB
Progress (2): 1.8/1.8 MB | 3.6/3.6 MB
Progress (2): 1.8/1.8 MB | 3.6/3.6 MB
Progress (2): 1.8/1.8 MB | 3.6/3.6 MB
Progress (2): 1.8/1.8 MB | 3.6 MB    
Progress (2): 1.8 MB | 3.6 MB    
                             
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/apache/lucene/lucene-core/8.11.2/lucene-core-8.11.2.jar (3.6 MB at 3.2 MB/s)
Downloaded from nexus-central: https://nexus-ci.onefiserv.net/repository/Maven_Central/org/apache/lucene/lucene-analyzers-common/8.11.2/lucene-analyzers-common-8.11.2.jar (1.8 MB at 1.5 MB/s)
[INFO] 
[INFO] --- clean:3.2.0:clean (default-clean) @ search-integration ---
[INFO] 
[INFO] --- resources:3.3.1:resources (default-resources) @ search-integration ---
[WARNING] Using platform encoding (UTF-8 actually) to copy filtered resources, i.e. build is platform dependent!
[INFO] Copying 1 resource from src/main/resources to target/classes
[INFO] 
[INFO] --- compiler:3.13.0:compile (default-compile) @ search-integration ---
[INFO] Recompiling the module because of changed dependency.
[WARNING] File encoding has not been set, using platform encoding UTF-8, i.e. build is platform dependent!
[INFO] Compiling 5 source files with javac [debug parameters release 21] to target/classes
[INFO] /newarch/apps/jenkins/sylp2nj1aue0001/workspace/s-Java_client-sysprin-pipeline-j-2/search-integration/src/main/java/rapid/searchintegration/service/ClientIndexer.java: /newarch/apps/jenkins/sylp2nj1aue0001/workspace/s-Java_client-sysprin-pipeline-j-2/search-integration/src/main/java/rapid/searchintegration/service/ClientIndexer.java uses or overrides a deprecated API.
[INFO] /newarch/apps/jenkins/sylp2nj1aue0001/workspace/s-Java_client-sysprin-pipeline-j-2/search-integration/src/main/java/rapid/searchintegration/service/ClientIndexer.java: Recompile with -Xlint:deprecation for details.
[INFO] 
[INFO] --- resources:3.3.1:testResources (default-testResources) @ search-integration ---
[WARNING] Using platform encoding (UTF-8 actually) to copy filtered resources, i.e. build is platform dependent!
[INFO] skip non existing resourceDirectory /newarch/apps/jenkins/sylp2nj1aue0001/workspace/s-Java_client-sysprin-pipeline-j-2/search-integration/src/test/resources
[INFO] 
[INFO] --- compiler:3.13.0:testCompile (default-testCompile) @ search-integration ---
[INFO] Recompiling the module because of changed dependency.
[WARNING] File encoding has not been set, using platform encoding UTF-8, i.e. build is platform dependent!
[INFO] Compiling 3 source files with javac [debug parameters release 21] to target/test-classes
[INFO] 
[INFO] --- surefire:3.2.5:test (default-test) @ search-integration ---
[INFO] Using auto detected provider org.apache.maven.surefire.junitplatform.JUnitPlatformProvider
[INFO] 
[INFO] -------------------------------------------------------
[INFO]  T E S T S
[INFO] -------------------------------------------------------
[INFO] Running rapid.searchintegration.service.ClientIndexerTest
17:14:16.518 [main] INFO rapid.searchintegration.service.ClientIndexer -- Lucene indexing completed. Total indexed: 1
17:14:16.577 [main] INFO rapid.searchintegration.service.ClientIndexer -- Lucene indexing completed. Total indexed: 1
17:14:16.603 [main] INFO rapid.searchintegration.service.ClientIndexer -- Lucene indexing completed. Total indexed: 1
17:14:16.610 [main] INFO rapid.searchintegration.service.ClientIndexer -- Lucene indexing completed. Total indexed: 1
17:14:16.617 [main] INFO rapid.searchintegration.service.ClientIndexer -- Lucene indexing completed. Total indexed: 1
17:14:16.623 [main] INFO rapid.searchintegration.service.ClientIndexer -- Lucene indexing completed. Total indexed: 1
17:14:16.628 [main] INFO rapid.searchintegration.service.ClientIndexer -- Lucene indexing completed. Total indexed: 1
17:14:16.635 [main] INFO rapid.searchintegration.service.ClientIndexer -- Lucene indexing completed. Total indexed: 2
[INFO] Tests run: 9, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.345 s -- in rapid.searchintegration.service.ClientIndexerTest
[INFO] Running rapid.searchintegration.service.SearchClientServiceTest
OpenJDK 64-Bit Server VM warning: Sharing is only supported for boot loader classes because bootstrap classpath has been appended
WARNING: A Java agent has been loaded dynamically (/newarch/apps/maven-repo/net/bytebuddy/byte-buddy-agent/1.17.5/byte-buddy-agent-1.17.5.jar)
WARNING: If a serviceability tool is in use, please run with -XX:+EnableDynamicAgentLoading to hide this warning
WARNING: If a serviceability tool is not in use, please run with -Djdk.instrument.traceUsage for more information
WARNING: Dynamic loading of agents will be disallowed by default in a future release
[INFO] Tests run: 2, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 1.025 s -- in rapid.searchintegration.service.SearchClientServiceTest
[INFO] Running rapid.searchintegration.web.SearchClientControllerTest
[INFO] Tests run: 4, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.061 s -- in rapid.searchintegration.web.SearchClientControllerTest
[INFO] 
[INFO] Results:
[INFO] 
[INFO] Tests run: 15, Failures: 0, Errors: 0, Skipped: 0
[INFO] 
[INFO] 
[INFO] --- jar:3.4.2:jar (default-jar) @ search-integration ---
[INFO] Building jar: /newarch/apps/jenkins/sylp2nj1aue0001/workspace/s-Java_client-sysprin-pipeline-j-2/search-integration/target/search-integration-0.0.1-SNAPSHOT.jar
[INFO] 
[INFO] --- spring-boot:3.4.2:repackage (default) @ search-integration ---
[INFO] Replacing main artifact /newarch/apps/jenkins/sylp2nj1aue0001/workspace/s-Java_client-sysprin-pipeline-j-2/search-integration/target/search-integration-0.0.1-SNAPSHOT.jar with repackaged archive, adding nested dependencies in BOOT-INF/.
[INFO] The original artifact has been renamed to /newarch/apps/jenkins/sylp2nj1aue0001/workspace/s-Java_client-sysprin-pipeline-j-2/search-integration/target/search-integration-0.0.1-SNAPSHOT.jar.original
[INFO] ------------------------------------------------------------------------
[INFO] Reactor Summary for trace-client-sysprin-service 0.0.1-SNAPSHOT:
[INFO] 
[INFO] trace-client-sysprin-service ....................... SUCCESS [  0.156 s]
[INFO] common-model ....................................... SUCCESS [ 36.497 s]
[INFO] common-api-dto ..................................... SUCCESS [  1.181 s]
[INFO] common-mapper ...................................... SUCCESS [  2.079 s]
[INFO] client-sysprin-writer .............................. SUCCESS [ 24.079 s]
[INFO] client-sysprin-reader .............................. SUCCESS [  0.925 s]
[INFO] gateway ............................................ SUCCESS [  7.414 s]
[INFO] search-integration ................................. SUCCESS [ 13.575 s]
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  01:26 min
[INFO] Finished at: 2025-08-07T17:14:17Z
[INFO] ------------------------------------------------------------------------
[Pipeline] script
[Pipeline] {
[Pipeline] tool
[Pipeline] tool
[Pipeline] withEnv
[Pipeline] {
[Pipeline] sh
+ head -n1 /newarch/apps/fortify/version.txt
Did you forget the `def` keyword? gfsPOMPropertyValue seems to be setting a field named command (to a value of type String) which could lead to memory leaks or other issues.
[Pipeline] sh
+ mvn help:evaluate -Dexpression=sonar.projectName -Dfortify.version=25.2.0 -q -DforceStdout
Did you forget the `def` keyword? gfsPOMPropertyValue seems to be setting a field named propertyValue (to a value of type String) which could lead to memory leaks or other issues.
[Pipeline] echo
pom property value = null
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // script
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Scan)
Stage "Scan" skipped due to when conditional
[Pipeline] getContext
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Release)
Stage "Release" skipped due to when conditional
[Pipeline] getContext
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Build container image)
Stage "Build container image" skipped due to when conditional
[Pipeline] getContext
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Scan container image)
Stage "Scan container image" skipped due to when conditional
[Pipeline] getContext
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Release container image)
Stage "Release container image" skipped due to when conditional
[Pipeline] getContext
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Deploy to DEMO)
Stage "Deploy to DEMO" skipped due to when conditional
[Pipeline] getContext
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (DEMO regression test)
Stage "DEMO regression test" skipped due to when conditional
[Pipeline] getContext
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Deploy to QA)
Stage "Deploy to QA" skipped due to when conditional
[Pipeline] getContext
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (QA regression test)
Stage "QA regression test" skipped due to when conditional
[Pipeline] getContext
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Dynamic Scan)
Stage "Dynamic Scan" skipped due to when conditional
[Pipeline] getContext
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Declarative: Post Actions)
[Pipeline] script
[Pipeline] {
[Pipeline] echo
notify gitlab
[Pipeline] withCredentials
Masking supported pattern matches of $token
[Pipeline] {
Did you forget the `def` keyword? gfsNotifyGitlab seems to be setting a field named state (to a value of type String) which could lead to memory leaks or other issues.
Did you forget the `def` keyword? gfsNotifyGitlab seems to be setting a field named state (to a value of type String) which could lead to memory leaks or other issues.
[Pipeline] echo
project id = issuers%2Ffos-modernization%2Fplastic%2Frapid%2FRAPID-Rapid-microservices-Java
[Pipeline] echo
api url = "https://gitlab.onefiserv.net/api/v4/projects/issuers%2Ffos-modernization%2Fplastic%2Frapid%2FRAPID-Rapid-microservices-Java/statuses/9a32a137f2082bf0277c1f39b19e6673f063f2a8"
[Pipeline] echo
{"state": "success", "target_url": "https://nsajenkins.fiserv.one/job/RAPID-Rapid-microservices-Java/job/client-sysprin-pipeline-j/1/", "description": "built by Jenkins @ https://nsajenkins.fiserv.one"}
[Pipeline] httpRequest
HttpMethod: POST
URL: https://gitlab.onefiserv.net/api/v4/projects/issuers%2Ffos-modernization%2Fplastic%2Frapid%2FRAPID-Rapid-microservices-Java/statuses/9a32a137f2082bf0277c1f39b19e6673f063f2a8
Content-Type: application/json
Authorization: *****
Sending request to url: https://gitlab.onefiserv.net/api/v4/projects/issuers%2Ffos-modernization%2Fplastic%2Frapid%2FRAPID-Rapid-microservices-Java/statuses/9a32a137f2082bf0277c1f39b19e6673f063f2a8
Response Code: HTTP/1.1 201 Created
Success: Status code 201 is in the accepted range: 200:204,400:403
[Pipeline] }
[Pipeline] // withCredentials
[Pipeline] tool
[Pipeline] tool
[Pipeline] withEnv
[Pipeline] {
[Pipeline] tool
[Pipeline] tool
[Pipeline] withEnv
[Pipeline] {
[Pipeline] sh
+ head -n1 /newarch/apps/fortify/version.txt
Did you forget the `def` keyword? gfsPOMPropertyValue seems to be setting a field named command (to a value of type String) which could lead to memory leaks or other issues.
[Pipeline] sh
+ mvn help:evaluate -Dexpression=project.version -Dfortify.version=25.2.0 -q -DforceStdout
Did you forget the `def` keyword? gfsPOMPropertyValue seems to be setting a field named propertyValue (to a value of type String) which could lead to memory leaks or other issues.
[Pipeline] echo
pom property value = 0.0.1-SNAPSHOT
[Pipeline] }
[Pipeline] // withEnv
Did you forget the `def` keyword? gfsCloudPipelineV2 seems to be setting a field named projectVersion (to a value of type String) which could lead to memory leaks or other issues.
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] sh
+ echo clean up workspace
clean up workspace
[Pipeline] deleteDir
[Pipeline] }
[Pipeline] // script
[Pipeline] }
[Pipeline] // stage
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // timeout
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // node
[Pipeline] sh
+ echo project version = 0.0.1-SNAPSHOT
project version = 0.0.1-SNAPSHOT
[Pipeline] }
[Pipeline] // dir
[Pipeline] }
[Pipeline] // node
[Pipeline] End of Pipeline
Finished: SUCCESS

