<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
		 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
		 xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>

	<parent>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-parent</artifactId>
		<version>3.5.0</version>
		<relativePath/>
	</parent>

	<groupId>admin</groupId>
	<artifactId>admin</artifactId>
	<version>0.0.1-SNAPSHOT</version>
	<name>admin</name>
	<description>Rapid Admin</description>

	<properties>
		<java.version>21</java.version>
		<mapstruct.version>1.5.5.Final</mapstruct.version>
		<spring-boot.version>3.5.0</spring-boot.version>

		<sonar.projectName>GFS-FOS-${project.artifactId}</sonar.projectName>
		<sonar.projectVersion>${project.version}</sonar.projectVersion>
		<sonar.java.binaries>target/classes</sonar.java.binaries>
		<sonar.tests>src/test</sonar.tests>
		<sonar.sources>src/main</sonar.sources>

		<sonatype.appId>APM0012115_gfs-fos-trace-microservices-release-v1</sonatype.appId>
		<fortify.sscApplicationName>APM0012115</fortify.sscApplicationName>
		<fortify.sscApplicationVersion>gfs-fos-trace-microservices-release-v1</fortify.sscApplicationVersion>

		<rundeck.job.option.name>Service</rundeck.job.option.name>
		<rundeck.job.option.value>${project.artifactId}</rundeck.job.option.value>
		<rundeck.url>https://rundeck.1dc.com</rundeck.url>
		<rundeck.token>AbWbrusvtE5DwpX9fWqnXtx9MHqYKs1G</rundeck.token>
		<rundeck.job>8ba40041-e885-4e6d-a69a-004dce3b48cf</rundeck.job>
		<rundeck.job.params>SERVICE_NAME=${project.artifactId},VERSION=${project.version},NAMESPACE=trace-dev-comm-app,CONFIG_NAME=trace-dev-comm-app-1,TYPE=springboot,CLUSTER=${cluster.url}</rundeck.job.params>
		<cluster.url>https://api.syosxfftsm0001.fiserv.one:6443/</cluster.url>
	</properties>

	<scm>
		<developerConnection>scm:git:git@gitlab.onefiserv.net:issuers/fos-modernization/plastic/rapid/RAPID-Rapid-microservices-Java.git</developerConnection>
		<tag>HEAD</tag>
	</scm>

	<dependencies>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-web</artifactId>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-data-jpa</artifactId>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-validation</artifactId>
		</dependency>
		<dependency>
			<groupId>com.h2database</groupId>
			<artifactId>h2</artifactId>
			<scope>runtime</scope>
		</dependency>
		<dependency>
			<groupId>org.liquibase</groupId>
			<artifactId>liquibase-core</artifactId>
		</dependency>
		<dependency>
			<groupId>org.projectlombok</groupId>
			<artifactId>lombok</artifactId>
			<version>1.18.30</version>
			<scope>provided</scope>
		</dependency>
		<dependency>
			<groupId>org.springdoc</groupId>
			<artifactId>springdoc-openapi-starter-webmvc-ui</artifactId>
			<version>2.8.8</version>
		</dependency>
		<dependency>
			<groupId>com.microsoft.sqlserver</groupId>
			<artifactId>mssql-jdbc</artifactId>
			<version>12.10.0.jre11</version>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-cache</artifactId>
		</dependency>
		<dependency>
			<groupId>com.github.ben-manes.caffeine</groupId>
			<artifactId>caffeine</artifactId>
		</dependency>
		<dependency>
			<groupId>org.apache.lucene</groupId>
			<artifactId>lucene-core</artifactId>
			<version>8.11.2</version>
		</dependency>
		<dependency>
			<groupId>org.apache.lucene</groupId>
			<artifactId>lucene-analyzers-common</artifactId>
			<version>8.11.2</version>
		</dependency>
		<dependency>
			<groupId>org.apache.lucene</groupId>
			<artifactId>lucene-queryparser</artifactId>
			<version>8.11.4</version>
		</dependency>
		<dependency>
			<groupId>org.mapstruct</groupId>
			<artifactId>mapstruct</artifactId>
			<version>${mapstruct.version}</version>
		</dependency>
		<dependency>
			<groupId>org.mapstruct</groupId>
			<artifactId>mapstruct-processor</artifactId>
			<version>${mapstruct.version}</version>
			<scope>provided</scope>
		</dependency>
	</dependencies>

	<build>
		<plugins>
			<plugin>
				<groupId>org.apache.maven.plugins</groupId>
				<artifactId>maven-compiler-plugin</artifactId>
				<version>3.13.0</version>
				<configuration>
					<release>${java.version}</release>
					<annotationProcessorPaths>
						<path>
							<groupId>org.projectlombok</groupId>
							<artifactId>lombok</artifactId>
							<version>1.18.38</version>
						</path>
						<path>
							<groupId>org.mapstruct</groupId>
							<artifactId>mapstruct-processor</artifactId>
							<version>${mapstruct.version}</version>
						</path>
					</annotationProcessorPaths>
				</configuration>
			</plugin>

			<plugin>
				<groupId>org.springframework.boot</groupId>
				<artifactId>spring-boot-maven-plugin</artifactId>
				<version>3.4.2</version>
				<executions>
					<execution>
						<goals>
							<goal>repackage</goal>
						</goals>
					</execution>
				</executions>
			</plugin>

			<plugin>
				<groupId>org.jacoco</groupId>
				<artifactId>jacoco-maven-plugin</artifactId>
				<version>0.8.13</version>
				<configuration>
					<append>true</append>
				</configuration>
				<executions>
					<execution>
						<id>prepare-agent</id>
						<goals>
							<goal>prepare-agent</goal>
						</goals>
					</execution>
					<execution>
						<id>check</id>
						<goals>
							<goal>check</goal>
						</goals>
						<configuration>
							<rules>
								<rule>
									<element>CLASS</element>
									<limits>
										<limit>
											<counter>LINE</counter>
											<value>COVEREDRATIO</value>
											<minimum>0.0</minimum>
										</limit>
										<limit>
											<counter>BRANCH</counter>
											<value>COVEREDRATIO</value>
											<minimum>0.0</minimum>
										</limit>
									</limits>
								</rule>
							</rules>
						</configuration>
					</execution>
					<execution>
						<id>report</id>
						<phase>prepare-package</phase>
						<goals>
							<goal>report</goal>
						</goals>
					</execution>
				</executions>
			</plugin>
			<plugin>
				<groupId>com.fortify.sca.plugins.maven</groupId>
				<artifactId>sca-maven-plugin</artifactId>
				<version>18.10</version>
				<dependencies>
					<dependency>
						<groupId>org.codehaus.plexus</groupId>
						<artifactId>plexus-utils</artifactId>
						<version>3.3.0</version>
					</dependency>
					<dependency>
						<groupId>org.apache.maven</groupId>
						<artifactId>maven-core</artifactId>
						<version>3.9.9</version>
					</dependency>
					<dependency>
						<groupId>org.apache.maven</groupId>
						<artifactId>maven-settings</artifactId>
						<version>3.9.9</version>
					</dependency>
				</dependencies>
			</plugin>
			<plugin>
				<groupId>org.sonarsource.scanner.maven</groupId>
				<artifactId>sonar-maven-plugin</artifactId>
				<version>3.7.0.1746</version>
			</plugin>
		</plugins>
	</build>

	<distributionManagement>
		<repository>
			<id>nexus-ci-releases</id>
			<url>https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases</url>
		</repository>
	</distributionManagement>
</project>


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






