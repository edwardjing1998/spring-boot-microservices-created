<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">

  <!-- ────── 1. 基本信息 ─────────────────────────────────────────── -->
  <modelVersion>4.0.0</modelVersion>

  <!-- 使用 Spring Boot 父 POM → 自动带入 BOM 与插件版本 -->
  <parent>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-parent</artifactId>
    <version>3.4.3</version>
    <relativePath/>             <!-- 从仓库查找 -->
  </parent>

  <groupId>admin</groupId>
  <artifactId>admin</artifactId>
  <version>0.0.1-SNAPSHOT</version>
  <name>Rapid Admin</name>
  <description>Rapid Admin micro-services (Java)</description>

  <properties>
    <!-- Java 版本；父 POM 会把它映射到 maven-compiler-plugin -->
    <java.version>21</java.version>
  </properties>

  <!-- ────── 2. 项目依赖 ─────────────────────────────────────────── -->
  <dependencies>
    <!-- Web（默认带 tomcat-embed-core 10.1.20，由 BOM 管） -->
    <dependency>
      <groupId>org.springframework.boot</groupId>
      <artifactId>spring-boot-starter-web</artifactId>
    </dependency>

    <!-- Spring Data JPA -->
    <dependency>
      <groupId>org.springframework.boot</groupId>
      <artifactId>spring-boot-starter-data-jpa</artifactId>
    </dependency>

    <!-- H2 数据库（仅开发/测试阶段 runtime） -->
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

    <!-- Lombok：BOM 已有 1.18.30，可省 version -->
    <dependency>
      <groupId>org.projectlombok</groupId>
      <artifactId>lombok</artifactId>
      <scope>provided</scope>
    </dependency>

    <!-- SpringDoc OpenAPI（需要手动定版本） -->
    <dependency>
      <groupId>org.springdoc</groupId>
      <artifactId>springdoc-openapi-starter-webmvc-ui</artifactId>
      <version>2.2.0</version>
    </dependency>

    <!-- SQL Server JDBC 驱动 -->
    <dependency>
      <groupId>com.microsoft.sqlserver</groupId>
      <artifactId>mssql-jdbc</artifactId>
      <version>12.10.0.jre11</version>
    </dependency>

    <!-- 缓存（Spring + Caffeine） -->
    <dependency>
      <groupId>org.springframework.boot</groupId>
      <artifactId>spring-boot-starter-cache</artifactId>
    </dependency>
    <dependency>
      <groupId>com.github.ben-manes.caffeine</groupId>
      <artifactId>caffeine</artifactId>
    </dependency>

    <!-- JMS（如果需要） -->
    <dependency>
      <groupId>org.springframework</groupId>
      <artifactId>spring-jms</artifactId>
    </dependency>

    <!-- Apache Lucene -->
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

  <!-- ────── 3. 构建插件 ─────────────────────────────────────────── -->
  <build>
    <plugins>
      <!-- 编译插件：版本由父 POM 插件管理指定，可省 <version> -->
      <plugin>
        <groupId>org.apache.maven.plugins</groupId>
        <artifactId>maven-compiler-plugin</artifactId>
        <configuration>
          <release>${java.version}</release>
        </configuration>
      </plugin>

      <!-- Spring Boot 插件：版本同样由父 POM 管控 -->
      <plugin>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-maven-plugin</artifactId>
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

  <!-- ────── 4. （可选）显式固定 Tomcat 版本 ──────────────────── -->
  <!-- 若 Nexus 依旧拦截 10.1.20，可取消注释以下块，强制回落到 10.1.18
  <dependencyManagement>
    <dependencies>
      <dependency>
        <groupId>org.apache.tomcat.embed</groupId>
        <artifactId>tomcat-embed-core</artifactId>
        <version>10.1.18</version>
      </dependency>
    </dependencies>
  </dependencyManagement>
  -->

</project>


- name: Dump effective POM
  run: mvn -q help:effective-pom -Doutput=effective.xml

- name: Grep tomcat version
  run: grep -n "<tomcat-embed-core" -A1 effective.xml || true

