# aws_infrastructures

## AWS ECS Application
![Architecture diagram](infras/connect.png)

* **End-to-End CI/CD Modernization:** Complete CI/CD migration from CodePipeline to a GitHub Actions. This reduced pipeline maintenance overhead by 40%.

* **Security-First Pipeline Integration:** Replaced PAT key, webhooks credentials with OpenID Connect (OIDC) authentication between GitHub Actions and AWS, eliminating the risk of static key leakage and ensured least-privilege principles.

* **ECS Cluster Management:** Designed and managed a highly available Amazon ECS architecture running on EC2 instances across private subnets. configured Auto Scaling Groups (ASG) based on CPU/Memory utilization to handle traffic spikes for frontend and backend microservices.

* **Database on Container Architecture:** Managed self-hosted MongoDB clusters running within ECS, utilizing Amazon EFS (Elastic File System) for persistent storage and backups.

* **Network Security & Traffic Flow:** Configured Application Load Balancers (ALB) with path-based listener rules to route traffic between UI and Backend containers. Hardened security posture by implementing Akamai WAF at the edge and managing AWS Security Groups to strictly isolate database and app tiers.

* **Observability & Monitoring:** Centralized logging and metrics using Amazon CloudWatch and SNS. Configured automated alerts for "Unhealthy Host" and cloudwatch synthetics canary 

* **Cost Reduction:** Reduced CI/CD operational costs by ~35% by deprecating AWS CodePipeline active pipeline fees and optimizing GitHub Actions runner minutes through aggressive caching and matrix build strategies.

* **Build Time Optimization:** Decreased average build-and-deploy times from **25 minutes to 15 minutes by migrating to GitHub Actions

<br>

## S3 - CloudFront Application
![Architecture diagram](infras/s3-cloudfront.png)

* **Serverless CI/CD Architecture:** Designed and implemented a serverless deployment pipeline for a high-traffic static website using AWS Lambda, CodeBuild, and S3, reducing server management overhead to zero.

* **Content Delivery & Security:** Configured Amazon CloudFront as a CDN to lower global latency by ~60%, integrated with AWS WAF (Web Application Firewall) to block malicious traffic (SQL injection, XSS) at the edge.

* **Cost Reduction:** Slashed CI/CD operational costs by 30% by eliminating CodeBuild build minutes and Lambda invocation fees by migrating to GitHub Actions.

* **Deployment Velocity:** Decreased build-to-deploy time by 50% by utilizing GitHub Actions job execution and removing the latency of cross-service triggers.

<br>

## AWS Cost Efficient Application
![Architecture diagram](infras/ai_ecs.png)

* **Cost Savings:** Reduced cloud infrastructure monthly burn rate by nearly $1500 in 4 environments by running data services as infrastructure as service

* **Performance:** Improved application response time by 200ms by placing Data and API layers in the same private subnet and utilizing internal Network Load Balancers.

* **Efficiency:** Eliminated manual image management overhead by implementing JFrog lifecycle policies, automatically cleaning up unused artifacts older than 30 days.

* **Observability** Established a centralized observability stack using AWS CloudWatch for log aggregation, synthetic monitoring, and alarms routed via SNS

* **Security** Hardened infrastructure security by deploying a Bastion Host for controlled SSH access to private data subnets and implementing granular Security Group rules to minimize the attack surface.

<br>

## AWS EKS Application
![Architecture diagram](infras/support.png)

<br>