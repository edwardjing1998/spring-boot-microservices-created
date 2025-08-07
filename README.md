+ mvn clean deploy -DskipTests=true
[INFO] Scanning for projects...
[INFO] ------------------------------------------------------------------------
[INFO] Reactor Build Order:
[INFO] 
[INFO] trace-client-sysprin-service                                       [pom]
[INFO] common-model                                                       [jar]
[INFO] common-api-dto                                                     [jar]
[INFO] common-mapper                                                      [jar]
[INFO] client-sysprin-writer                                              [jar]
[INFO] client-sysprin-reader                                              [jar]
[INFO] gateway                                                            [jar]
[INFO] search-integration                                                 [jar]
[INFO] 
[INFO] -----< trace-client-sysprin-service:trace-client-sysprin-service >------
[INFO] Building trace-client-sysprin-service 0.0.1                        [1/8]
[INFO]   from pom.xml
[INFO] --------------------------------[ pom ]---------------------------------
[INFO] 
[INFO] --- clean:3.2.0:clean (default-clean) @ trace-client-sysprin-service ---
[INFO] 
[INFO] --- install:3.1.2:install (default-install) @ trace-client-sysprin-service ---
[INFO] Installing /newarch/apps/jenkins/sylp2nj1aue0002/workspace/elease_client-sysprin-pipeline-j/pom.xml to /newarch/apps/maven-repo/trace-client-sysprin-service/trace-client-sysprin-service/0.0.1/trace-client-sysprin-service-0.0.1.pom
[INFO] 
[INFO] --- deploy:3.1.2:deploy (default-deploy) @ trace-client-sysprin-service ---
[INFO] ------------------------------------------------------------------------
[INFO] Reactor Summary for trace-client-sysprin-service 0.0.1:
[INFO] 
[INFO] trace-client-sysprin-service ....................... FAILURE [  0.232 s]
[INFO] common-model ....................................... SKIPPED
[INFO] common-api-dto ..................................... SKIPPED
[INFO] common-mapper ...................................... SKIPPED
[INFO] client-sysprin-writer .............................. SKIPPED
[INFO] client-sysprin-reader .............................. SKIPPED
[INFO] gateway ............................................ SKIPPED
[INFO] search-integration ................................. SKIPPED
[INFO] ------------------------------------------------------------------------
[INFO] BUILD FAILURE
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  0.632 s
[INFO] Finished at: 2025-08-07T18:41:06Z
[INFO] ------------------------------------------------------------------------
[ERROR] Failed to execute goal org.apache.maven.plugins:maven-deploy-plugin:3.1.2:deploy (default-deploy) on project trace-client-sysprin-service: Deployment failed: repository element was not specified in the POM inside distributionManagement element or in -DaltDeploymentRepository=id::url parameter -> [Help 1]
[ERROR] 
[ERROR] To see the full stack trace of the errors, re-run Maven with the -e switch.
[ERROR] Re-run Maven using the -X switch to enable full debug logging.
[ERROR] 
[ERROR] For more information about the errors and possible solutions, please read the following articles:
[ERROR] [Help 1] http://cwiki.apache.org/confluence/display/MAVEN/MojoExecutionException
