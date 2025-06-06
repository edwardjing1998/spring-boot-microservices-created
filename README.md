<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
		 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
		 xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>

	<parent>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-parent</artifactId>
		<version>3.4.3</version> <!-- ✅ Use stable version -->
		<relativePath/> <!-- lookup parent from repository -->
	</parent>

	<groupId>admin</groupId>
	<artifactId>admin</artifactId>
	<version>0.0.1-SNAPSHOT</version>
	<name>admin</name>
	<description>Rapid Admin</description>

	<properties>
		<java.version>23</java.version>
	</properties>

	<dependencies>
		<!-- Exclude tomcat-embed-core -->
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-web</artifactId>
		</dependency>

		<!-- Spring Data JPA -->
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-data-jpa</artifactId>
		</dependency>

		<!-- H2 In-Memory Database -->
		<dependency>
			<groupId>com.h2database</groupId>
			<artifactId>h2</artifactId>
			<scope>runtime</scope>
		</dependency>

		<!-- Liquibase -->
		<dependency>
			<groupId>org.liquibase</groupId>
			<artifactId>liquibase-core</artifactId>
		</dependency>

		<!-- ✅ Lombok -->
		<dependency>
			<groupId>org.projectlombok</groupId>
			<artifactId>lombok</artifactId>
			<version>1.18.30</version> <!-- latest stable as of early 2025 -->
			<scope>provided</scope>
		</dependency>

		<dependency>
			<groupId>org.springdoc</groupId>
			<artifactId>springdoc-openapi-starter-webmvc-ui</artifactId>
			<version>2.2.0</version>
		</dependency>

		<dependency>
			<groupId>com.microsoft.sqlserver</groupId>
			<artifactId>mssql-jdbc</artifactId>
			<version>12.10.0.jre11</version> <!-- Match the DLL version -->
		</dependency>

		<!-- Spring Boot Starter for caching -->
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-cache</artifactId>
		</dependency>

		<dependency>
			<groupId>org.springframework</groupId>
			<artifactId>spring-jms</artifactId>
		</dependency>

		<!-- Caffeine cache library -->
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
	</dependencies>

	<build>
		<plugins>
			<plugin>
				<groupId>org.apache.maven.plugins</groupId>
				<artifactId>maven-compiler-plugin</artifactId>
				<version>3.13.0</version>
				<configuration>
					<release>21</release>
				</configuration>
			</plugin>

			<plugin>
				<groupId>org.springframework.boot</groupId>
				<artifactId>spring-boot-maven-plugin</artifactId>
				<version>3.4.3</version>
				<executions>
					<execution>
						<goals>
							<goal>repackage</goal>
						</goals>
					</execution>
				</executions>
			</plugin>
		</plugins>
	</build>

</project>


mvn -q help:effective-pom -Doutput=effective.xml

# ① 最直观：把整个 -D 选项包起来
mvn -q help:effective-pom '-Doutput=effective.xml'

# ② 或者用双引号
mvn -q help:effective-pom "-Doutput=effective.xml"

# ③ 还可以直接重定向到文件，省掉 -Doutput
mvn -q help:effective-pom > effective.xml




grep -n "<tomcat-embed-core" -A1 effective.xml
grep -n "<tomcat.version>"    -A0 effective.xml   # 是否有屬性覆寫


        <annotationProcessorPaths>
          <path>
            <groupId>org.projectlombok</groupId>
            <artifactId>lombok</artifactId>
            <version>1.18.34</version>
          </path>
        </annotationProcessorPaths>



Downloaded from Nexus: https://nexus-dev.onefiserv.net/repository/mvn-gl-flume-public-group/org/projectlombok/lombok/1.18.34/lombok-1.18.34.pom (1.5 kB at 1.2 kB/s)
Downloading from Nexus: https://nexus-dev.onefiserv.net/repository/mvn-gl-flume-public-group/org/projectlombok/lombok/1.18.34/lombok-1.18.34.jar
Downloaded from Nexus: https://nexus-dev.onefiserv.net/repository/mvn-gl-flume-public-group/org/projectlombok/lombok/1.18.34/lombok-1.18.34.jar (2.1 MB at 1.4 MB/s)
[INFO] Recompiling the module because of changed source code.
[INFO] Compiling 212 source files with javac [debug parameters release 21] to target\classes
[INFO] ------------------------------------------------------------------------
[INFO] BUILD FAILURE
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  12.255 s
[INFO] Finished at: 2025-06-05T19:32:45-05:00
[INFO] ------------------------------------------------------------------------
[ERROR] Failed to execute goal org.apache.maven.plugins:maven-compiler-plugin:3.13.0:compile (default-compile) on project admin: Fatal error compiling: java.lang.ExceptionInInitializerError: com.sun.tools.javac.code.TypeTag :: UNKNOWN -> [Help 1]
[ERROR]
[ERROR] To see the full stack trace of the errors, re-run Maven with the -e switch.
[ERROR] Re-run Maven using the -X switch to enable full debug logging.
[ERROR]
[ERROR] For more information about the errors and possible solutions, please read the following articles:
[ERROR] [Help 1] http://cwiki.apache.org/confluence/display/MAVEN/MojoExecutionException
PS C:\Users\F2LIPBX\spring_boot\2025-04-12\RAPIDadmin-microservices-java> 





