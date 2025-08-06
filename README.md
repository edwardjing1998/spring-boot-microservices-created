<!-- modular-monolith/pom.xml -->
<project xmlns="http://maven.apache.org/POM/4.0.0"
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0
                             https://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>trace-rapidreturn-hub</groupId>
    <artifactId>trace-rapidreturn-hub</artifactId>
    <name>trace rapid microservices</name>
    <description>trace rapid microservices</description>
    <version>0.0.1-SNAPSHOT</version>
    <packaging>pom</packaging>

    <properties>
        <java.version>21</java.version>
        <mvn-compiler.version>3.13.0</mvn-compiler.version>
        <mvn-plugin.version>3.4.2</mvn-plugin.version>
        <mapstruct.version>1.5.5.Final</mapstruct.version>
        <lombok.version>1.18.38</lombok.version>
        <openapi.version>2.8.8</openapi.version>
        <spring-boot.version>3.5.0</spring-boot.version>
        <spring-cloud.version>2025.0.0</spring-cloud.version>
        <maven-core.version>3.9.8</maven-core.version>
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

    <modules>
        <module>trace-rapidReturn-zipCode</module>
        <module>common-model</module>
        <module>common-api-dto</module>
        <module>common-mapper</module>
        <module>trace-rapidReturn-dailyMessage</module>
        <module>gateway</module>
        <module>trace-rapidReturn-robotLabel</module>
        <module>trace-rapidReturn-globalSettings</module>
        <module>trace-rapidReturn-mailType</module>
        <module>trace-rapidReturn-applicationEvent</module>
        <module>trace-rapidReturn-emailSetup</module>
    </modules>

    <dependencyManagement>
        <dependencies>
            <dependency>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-dependencies</artifactId>
                <version>3.5.0</version>
                <type>pom</type>
                <scope>import</scope>
            </dependency>
            <dependency>
                <groupId>org.springframework.cloud</groupId>
                <artifactId>spring-cloud-dependencies</artifactId>
                <version>${spring-cloud.version}</version>
                <type>pom</type>
                <scope>import</scope>
            </dependency>
        </dependencies>
    </dependencyManagement>

    <build>
        <pluginManagement>
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
                    <groupId>org.apache.maven.plugins</groupId>
                    <artifactId>maven-jar-plugin</artifactId>
                    <version>3.4.2</version>
                </plugin>
                <plugin>
                    <groupId>org.jacoco</groupId>
                    <artifactId>jacoco-maven-plugin</artifactId>
                    <version>${jacoco.version}</version>
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
                    <version>24.2.0</version>
                    <dependencies>
                        <dependency>
                            <groupId>org.codehaus.plexus</groupId>
                            <artifactId>plexus-utils</artifactId>
                            <version>3.3.0</version>
                        </dependency>
                        <dependency>
                            <groupId>org.apache.maven</groupId>
                            <artifactId>maven-core</artifactId>
                            <version>3.9.8</version>
                        </dependency>
                        <dependency>
                            <groupId>org.apache.maven</groupId>
                            <artifactId>maven-settings</artifactId>
                            <version>3.9.8</version>
                        </dependency>
                    </dependencies>
                </plugin>
                <plugin>
                    <groupId>org.sonarsource.scanner.maven</groupId>
                    <artifactId>sonar-maven-plugin</artifactId>
                    <version>3.7.0.1746</version>
                </plugin>
            </plugins>
        </pluginManagement>
    </build>
    <distributionManagement>
        <repository>
            <id>nexus-ci-releases</id>
            <url>https://nexus-ci.onefiserv.net/repository/mvn-na-issuer-distapp-coreservices-private-releases</url>
        </repository>
    </distributionManagement>


</project>







<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">

    <modelVersion>4.0.0</modelVersion>

    <parent>
        <groupId>trace-rapidreturn-hub</groupId>
        <artifactId>trace-rapidreturn-hub</artifactId>
        <version>0.0.1-SNAPSHOT</version>
    </parent>

    <artifactId>trace-rapidReturn-zipCode</artifactId>
    <version>0.0.1-SNAPSHOT</version>
    <name>trace-rapidReturn-zipCode</name>
    <description>trace-rapidReturn-zipCode</description>

    <packaging>jar</packaging>

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
            <groupId>org.springdoc</groupId>
            <artifactId>springdoc-openapi-starter-webmvc-ui</artifactId>
            <version>2.8.8</version>
        </dependency>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-actuator</artifactId>
        </dependency>

        <dependency>
            <groupId>com.h2database</groupId>
            <artifactId>h2</artifactId>
            <scope>runtime</scope>
        </dependency>

        <dependency>
            <groupId>org.projectlombok</groupId>
            <artifactId>lombok</artifactId>
            <version>${lombok.version}</version>
            <scope>provided</scope>
        </dependency>

        <dependency>
            <groupId>com.microsoft.sqlserver</groupId>
            <artifactId>mssql-jdbc</artifactId>
            <version>12.10.0.jre11</version>
        </dependency>

        <dependency>
            <groupId>org.mapstruct</groupId>
            <artifactId>mapstruct</artifactId>
            <version>${mapstruct.version}</version>
        </dependency>

        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-test</artifactId>
            <scope>test</scope>
        </dependency>

        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-test-autoconfigure</artifactId>
            <scope>test</scope>
        </dependency>
        <dependency>
            <groupId>rapid-rapidreturn-hub</groupId>
            <artifactId>common-model</artifactId>
            <version>0.0.1-SNAPSHOT</version>
            <scope>compile</scope>
        </dependency>
        <dependency>
            <groupId>rapid-rapidreturn-hub</groupId>
            <artifactId>common-mapper</artifactId>
            <version>0.0.1-SNAPSHOT</version>
            <scope>compile</scope>
        </dependency>

    </dependencies>
</project>


[ERROR] The build could not read 9 projects -> [Help 1]
[ERROR]
[ERROR]   The project rapid-rapidreturn-hub:common-model:0.0.1-SNAPSHOT (C:\Users\F2LIPBX\spring_boot\RAPID-Rapid-microservices-Java\common-model\pom.xml) has 1 error
[ERROR]     Non-resolvable parent POM for rapid-rapidreturn-hub:common-model:0.0.1-SNAPSHOT: The following artifacts could not be resolved: rapid-rapidreturn-hub:rapid-rapidreturn-hub:pom:0.0.1-SNAPSHOT (absent): Could not find artifact rapid-rapidreturn-hub:rapid-rapidreturn-hub:pom:0.0.1-SNAPSHOT in Nexus (https://nexus-dev.onefiserv.net/repository/mvn-gl-flume-public-group/) and 'parent.relativePath' points at wrong local POM @ line 8, column 13 -> [Help 2]




