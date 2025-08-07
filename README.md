stages:
  - build
  - dockerize

variables:
  SERVICE_NAME: "admin"
  SERVICE_VERSION: "0.0.1-SNAPSHOT"
  JAR_NAME: "${SERVICE_NAME}-${SERVICE_VERSION}.jar"
  DOCKER_IMAGE: "$CI_REGISTRY_IMAGE/${SERVICE_NAME}:${SERVICE_VERSION}"

build-admin:
  stage: build
  image: maven:3.9-eclipse-temurin-17
  script:
    - mvn clean install -DskipTests
  artifacts:
    paths:
      - target/${JAR_NAME}

dockerize-admin:
  stage: dockerize
  image: docker:latest
  services:
    - docker:dind
  variables:
    DOCKER_TLS_CERTDIR: ""
  before_script:
    - docker login -u "$CI_REGISTRY_USER" -p "$CI_REGISTRY_PASSWORD" "$CI_REGISTRY"
  script:
    - docker build --build-arg JAR_NAME=${JAR_NAME} -t $DOCKER_IMAGE -f docker/admin/Dockerfile .
    - docker push $DOCKER_IMAGE




stages:
  - build
  - dockerize

variables:
  SERVICE_NAME: "admin"
  SERVICE_VERSION: "0.0.1-SNAPSHOT"
  JAR_NAME: "${SERVICE_NAME}-${SERVICE_VERSION}.jar"
  DOCKER_IMAGE: "$CI_REGISTRY_IMAGE/${SERVICE_NAME}:${SERVICE_VERSION}"

build-admin:
  stage: build
  image: maven:3.9-eclipse-temurin-17
  script:
    - mvn clean install -DskipTests
  artifacts:
    paths:
      - target/${JAR_NAME}

dockerize-admin:
  stage: dockerize
  image: docker:latest
  services:
    - docker:dind
  variables:
    DOCKER_TLS_CERTDIR: ""
  before_script:
    - docker login -u "$CI_REGISTRY_USER" -p "$CI_REGISTRY_PASSWORD" "$CI_REGISTRY"
  script:
    - docker build --build-arg JAR_NAME=${JAR_NAME} -t $DOCKER_IMAGE -f docker/admin/Dockerfile .
    - docker push $DOCKER_IMAGE
