    <plugin>
      <groupId>org.apache.maven.plugins</groupId>
      <artifactId>maven-jar-plugin</artifactId>
      <version>3.3.0</version>          <!-- keep the plugin version you want -->
      <dependencies>
        <dependency>
          <groupId>org.codehaus.plexus</groupId>
          <artifactId>plexus-archiver</artifactId>
          <!-- pick a version your Nexus allows, e.g. 4.3.8 or 4.3.7 -->
          <version>4.3.8</version>
        </dependency>
      </dependencies>
    </plugin>


    mvn dependency:tree -Dincludes=org.apache.tomcat.embed:tomcat-embed-core



    # run from the folder that has pom.xml
mvn dependency:tree \
    -Dincludes=org.springframework.boot:spring-boot-starter-web \
    -Dverbose


<dependency>
  <groupId>org.apache.tomcat.embed</groupId>
  <artifactId>tomcat-embed-core</artifactId>
  <version>10.1.18</version> <!-- or any version security approves -->
</dependency>


  <exclusions>
    <exclusion>
      <groupId>org.springframework.boot</groupId>
      <artifactId>spring-boot-starter-tomcat</artifactId>
    </exclusion>
  </exclusions>






