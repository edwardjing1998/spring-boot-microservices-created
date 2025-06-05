[INFO] --- surefire:3.2.2:test (default-test) @ admin ---
[INFO] No tests to run.
[INFO] 
[INFO] --- jar:3.3.0:jar (default-jar) @ admin ---
Downloading from Nexus: https://nexus-dev.onefiserv.net/repository/mvn-gl-flume-public-group/org/codehaus/plexus/plexus-archiver/4.4.0/plexus-archiver-4.4.0.jar
[INFO] ------------------------------------------------------------------------
[INFO] BUILD FAILURE
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  12.032 s
[INFO] Finished at: 2025-06-05T14:26:27-05:00
[INFO] ------------------------------------------------------------------------
[ERROR] Failed to execute goal org.apache.maven.plugins:maven-jar-plugin:3.3.0:jar (default-jar) on project admin: Execution default-jar of goal org.apache.maven.plugins:maven-jar-
plugin:3.3.0:jar failed: Plugin org.apache.maven.plugins:maven-jar-plugin:3.3.0 or one of its dependencies could not be resolved: The following artifacts could not be resolved: org
.codehaus.plexus:plexus-archiver:jar:4.4.0 (absent): Could not transfer artifact org.codehaus.plexus:plexus-archiver:jar:4.4.0 from/to Nexus (https://nexus-dev.onefiserv.net/repository/mvn-gl-flume-public-group/): status code: 401, reason phrase: Unauthorized (401) -> [Help 1]
[ERROR]
[ERROR] To see the full stack trace of the errors, re-run Maven with the -e switch.
[ERROR] Re-run Maven using the -X switch to enable full debug logging.
[ERROR]
[ERROR] For more information about the errors and possible solutions, please read the following articles:
[ERROR] [Help 1] http://cwiki.apache.org/confluence/display/MAVEN/PluginResolutionException
PS C:\Users\F2LIPBX\spring_boot\2025-04-12\RAPIDadmin-microservices-java> 
