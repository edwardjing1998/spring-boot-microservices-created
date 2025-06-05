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



    ----------->>> REQUESTED ITEM IS QUARANTINED -------------------->>> FOR DETAILS SEE ------>>> https://sonatype.fiserv.one/ui/links/malware-defense/repositories/quarantinedComponent/OTIwNjk3NWQwZWJhNDRjZDllYWE5NzA1MDJkYzRmMTY <<<------ (403)
6718Error: dependency: org.apache.tomcat.embed:tomcat-embed-core:jar:10.1.36 (compile)
6719Error: 	Could not transfer artifact org.apache.tomcat.embed:tomcat-embed-core:jar:10.1.36 from/to Nexus (https://nexus-dev.onefiserv.net/repository/mvn-gl-flume-public-group/): status code: 403, reason phrase: -------------------->>> REQUESTED ITEM IS QUARANTINED ---


