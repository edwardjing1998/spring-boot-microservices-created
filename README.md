Running with gitlab-runner 16.3.3 (ed9cebb1)
  on gitlab-runner-generic-16-3-3-6ff9ccff4b-hqg6c seqEosqd, system ID: r_Uy8vX4NqW6MQ
Resolving secrets
00:00
Preparing the "kubernetes" executor
00:00
Using Kubernetes namespace: gitlab-prod
Using Kubernetes executor with image fmk.nexus-ci.onefiserv.net/org/is/com.fiserv.issuer/fs-container-springboot-x86:3.0.8 ...
Using attach strategy to execute scripts...
Preparing environment
00:13
Waiting for pod gitlab-prod/runner-seqeosqd-project-66536-concurrent-0-eda7wfpc to be running, status is Pending
Waiting for pod gitlab-prod/runner-seqeosqd-project-66536-concurrent-0-eda7wfpc to be running, status is Pending
	ContainersNotReady: "containers with unready status: [build helper]"
	ContainersNotReady: "containers with unready status: [build helper]"
Waiting for pod gitlab-prod/runner-seqeosqd-project-66536-concurrent-0-eda7wfpc to be running, status is Pending
	ContainersNotReady: "containers with unready status: [build helper]"
	ContainersNotReady: "containers with unready status: [build helper]"
Waiting for pod gitlab-prod/runner-seqeosqd-project-66536-concurrent-0-eda7wfpc to be running, status is Pending
	ContainersNotReady: "containers with unready status: [build helper]"
	ContainersNotReady: "containers with unready status: [build helper]"
Running on runner-seqeosqd-project-66536-concurrent-0-eda7wfpc via gitlab-runner-generic-16-3-3-6ff9ccff4b-hqg6c...
Getting source from Git repository
00:03
Fetching changes with git depth set to 20...
Initialized empty Git repository in /builds/issuers/fos-modernization/plastic/rapid/RAPID-Rapid-microservices-Java/.git/
Created fresh repository.
Checking out 04cd6863 as detached HEAD (ref is release/rapid-microservices-Java)...
Skipping Git submodules setup
Executing "step_script" stage of the job script
00:00
$ mvn clean install -DskipTests
/scripts-66536-16904927/step_script: line 178: mvn: command not found
Cleaning up project directory and file based variables
00:01
ERROR: Job failed: command terminated with exit code 1
