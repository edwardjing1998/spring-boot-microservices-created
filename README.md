
Search job log
Running with gitlab-runner 16.3.3 (ed9cebb1)
  on gitlab-runner-generic-16-3-3-6ff9ccff4b-2t7dz hSxVDZhT, system ID: r_ctSX9um6Q1Bi
Resolving secrets
00:00
Preparing the "kubernetes" executor
00:00
Using Kubernetes namespace: gitlab-prod
Using Kubernetes executor with image fmk.nexus-ci.onefiserv.net/org/is/com.fiserv.issuer/fs-container-springboot-x86:3.0.8 ...
Using attach strategy to execute scripts...
Preparing environment
00:07
Waiting for pod gitlab-prod/runner-hsxvdzht-project-66536-concurrent-0-nonj6h6b to be running, status is Pending
Waiting for pod gitlab-prod/runner-hsxvdzht-project-66536-concurrent-0-nonj6h6b to be running, status is Pending
	ContainersNotReady: "containers with unready status: [build helper]"
	ContainersNotReady: "containers with unready status: [build helper]"
Running on runner-hsxvdzht-project-66536-concurrent-0-nonj6h6b via gitlab-runner-generic-16-3-3-6ff9ccff4b-2t7dz...
Getting source from Git repository
00:01
Fetching changes with git depth set to 20...
Initialized empty Git repository in /builds/issuers/fos-modernization/plastic/rapid/RAPID-Rapid-microservices-Java/.git/
Created fresh repository.
Checking out ad688fde as detached HEAD (ref is release/rapid-microservices-Java)...
Skipping Git submodules setup
Executing "step_script" stage of the job script
00:01
$ export MAVEN_HOME=/newarch/apps/apache-maven
$ export JAVA_HOME=/newarch/apps/openjdk21
$ export PATH=$MAVEN_HOME/bin:$JAVA_HOME/bin:$PATH
$ mvn clean install -DskipTests
/scripts-66536-16905071/step_script: line 183: mvn: command not found
Cleaning up project directory and file based variables
00:00
ERROR: Job failed: command terminated with exit code 1
