bulk_card:

Case_number	char	NO	12
PI_ID	char	NO	16
Bulk_PI_ID	char	NO	16
in_date	datetime	NO	NULL


Failed_Trans

case_number	char	YES	12
type	smallint	YES	NULL
command_line	varchar	YES	255
system_type	varchar	YES	50
retry_count	smallint	YES	NULL
date_time	datetime	YES	NULL
cycle	varchar	YES	1
trans_no	numeric	YES	NULL


1. Container Registry
* Which container registry do you use for storing Docker/OCI images (e.g. Nexus Repository Manager, Docker Hub, ACR, ECR)?
* How are your registry namespaces or repositories organized for dev, staging, and production?

1. Container Runtime & Orchestration
    * Where do containerized services actually run? (e.g. Kubernetes, plain Docker on VMs)
    * If Kubernetes‐based, do you use a managed cluster (EKS/GKE/AKS/OpenShift) or self‐managed?
    * 
2. CI/CD Pipeline Tooling
    * Which CI/CD system builds and publishes images? (e.g. GitHub Actions, GitLab CI, Jenkins)
    * What or how to trigger a build—push to main branch, tag, pull request merge, manual job, or schedule?
3. Build & Deployment Workflow
    * Do you have a standard pipeline definition (YAML/script) that runs docker build and pushes images automatically?
    * How are builds promoted between environments (e.g. dev → staging → prod)? Are those promotions automated or manual?

4. Local Development Workflow
    * How do developers build and test services locally? (e.g. plain docker build && docker run, docker‐compose, Tilt, Skaffold)
