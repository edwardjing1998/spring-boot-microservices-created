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

