stages:
  - build
  - docker-build

variables:
  JAR_NAME: admin-0.0.1-SNAPSHOT.jar
  DOCKER_IMAGE_NAME: admin
  DOCKER_TAG: "0.0.1"

build_admin:
  stage: build
  image: fmk.nexus-ci.onefiserv.net/org/is/com.fiserv.issuer/fs-container-springboot-x86:3.0.8
  before_script:
    - export MAVEN_HOME=/newarch/apps/apache-maven
    - export JAVA_HOME=/newarch/apps/openjdk21
    - export PATH=$MAVEN_HOME/bin:$JAVA_HOME/bin:$PATH
  script:
    - mvn clean install -DskipTests
  artifacts:
    paths:
      - target/${JAR_NAME}
    expire_in: 1 hour

docker_build_admin:
  stage: docker-build
  image: docker:latest
  services:
    - docker:dind
  variables:
    DOCKER_DRIVER: overlay2
  before_script:
    - docker info
  script:
    - docker build --build-arg JAR_NAME=${JAR_NAME} -t ${DOCKER_IMAGE_NAME}:${DOCKER_TAG} -f Dockerfile .
    - docker images
