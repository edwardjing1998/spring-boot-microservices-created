[INFO] rapid-case-service ................................. SUCCESS [  0.386 s]
[INFO] gateway ............................................ FAILURE [ 12.477 s]
[INFO] common-model ....................................... SKIPPED
[INFO] common-api-dto ..................................... SKIPPED
[INFO] common-mapper ...................................... SKIPPED
[INFO] review-deleted-case ................................ SKIPPED
[INFO] service-b .......................................... SKIPPED
[INFO] service-c .......................................... SKIPPED
[INFO] ------------------------------------------------------------------------
[INFO] BUILD FAILURE
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  13.488 s
[INFO] Finished at: 2025-06-21T16:38:52-05:00
[INFO] ------------------------------------------------------------------------
[ERROR] Failed to execute goal org.apache.maven.plugins:maven-jar-plugin:3.3.0:jar (default-jar) on project gateway: Execution default-jar of goal org.apache.maven.plugins:maven-ja
r-plugin:3.3.0:jar failed: Plugin org.apache.maven.plugins:maven-jar-plugin:3.3.0 or one of its dependencies could not be resolved: The following artifacts could not be resolved: o
rg.codehaus.plexus:plexus-archiver:jar:4.4.0 (absent): Could not transfer artifact org.codehaus.plexus:plexus-archiver:jar:4.4.0 from/to Nexus (https://nexus-dev.onefiserv.net/repo
sitory/mvn-gl-flume-public-group/): status code: 403, reason phrase: -------------------->>> REQUESTED ITEM IS QUARANTINED -------------------->>> FOR DETAILS SEE ------>>> https://sonatype.fiserv.one/ui/links/malware-defense/repositories/quarantinedComponent/MDEwODZlYzVhNTMxNDFmZWE0ZDlkM2M1M2M3NTc2MTk <<<------ (403) -> [Help 1]
[ERROR]
[ERROR] To see the full stack trace of the errors, re-run Maven with the -e switch.
[ERROR] Re-run Maven using the -X switch to enable full debug logging.
[ERROR]
[ERROR] For more information about the errors and possible solutions, please read the following articles:
[ERROR] [Help 1] http://cwiki.apache.org/confluence/display/MAVEN/PluginResolutionException
[ERROR]
[ERROR] After correcting the problems, you can resume the build with the command
[ERROR]   mvn <args> -rf :gateway
