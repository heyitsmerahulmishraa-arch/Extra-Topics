# Complete Deployment & Cloud Engineering Mastery Checklist

## 1. Deployment Fundamentals

- [ ] What is deployment?
- [ ] Development vs staging vs production
- [ ] Build vs deploy
- [ ] Application runtime
- [ ] Server
- [ ] Client
- [ ] Infrastructure
- [ ] Infrastructure as Code
- [ ] Configuration
- [ ] Environment variables
- [ ] Secrets
- [ ] Deployment artifacts
- [ ] Release
- [ ] Rollback
- [ ] Blue-green deployment
- [ ] Canary deployment
- [ ] Rolling deployment
- [ ] Zero-downtime deployment

---

## 2. Linux Server Fundamentals

- [ ] Linux filesystem
- [ ] Processes
- [ ] Services
- [ ] Users
- [ ] Groups
- [ ] Permissions
- [ ] SSH
- [ ] SSH keys
- [ ] Environment variables
- [ ] Ports
- [ ] Firewall
- [ ] System logs
- [ ] Process monitoring
- [ ] Disk management
- [ ] Memory management
- [ ] CPU monitoring
- [ ] Networking commands
- [ ] Package managers
- [ ] Systemd
- [ ] Cron jobs

### Important Commands

- [ ] `ssh`
- [ ] `scp`
- [ ] `rsync`
- [ ] `curl`
- [ ] `wget`
- [ ] `ss`
- [ ] `netstat`
- [ ] `top`
- [ ] `htop`
- [ ] `ps`
- [ ] `kill`
- [ ] `systemctl`
- [ ] `journalctl`
- [ ] `df`
- [ ] `du`
- [ ] `free`
- [ ] `uptime`

---

## 3. Networking Fundamentals

- [ ] What is a network?
- [ ] IP address
- [ ] IPv4
- [ ] IPv6
- [ ] MAC address
- [ ] Port
- [ ] Protocol
- [ ] TCP
- [ ] UDP
- [ ] HTTP
- [ ] HTTPS
- [ ] DNS
- [ ] DHCP
- [ ] NAT
- [ ] Routing
- [ ] Packets
- [ ] Subnet
- [ ] CIDR
- [ ] Gateway
- [ ] Firewall
- [ ] Proxy
- [ ] Reverse proxy
- [ ] Load balancer

### Commands

- [ ] `ping`
- [ ] `curl`
- [ ] `dig`
- [ ] `nslookup`
- [ ] `traceroute`
- [ ] `ip`
- [ ] `ss`

---

## 4. DNS

- [ ] What is DNS?
- [ ] Domain
- [ ] Nameserver
- [ ] DNS resolver
- [ ] DNS records
- [ ] A record
- [ ] AAAA record
- [ ] CNAME
- [ ] MX
- [ ] TXT
- [ ] NS
- [ ] TTL
- [ ] DNS propagation
- [ ] Subdomains
- [ ] DNS routing

---

## 5. HTTP & HTTPS

- [ ] HTTP request
- [ ] HTTP response
- [ ] Methods
- [ ] Headers
- [ ] Status codes
- [ ] Cookies
- [ ] Sessions
- [ ] HTTPS
- [ ] TLS
- [ ] Certificates
- [ ] Certificate renewal
- [ ] Reverse proxy
- [ ] Keep-alive
- [ ] Compression
- [ ] Caching

---

## 6. AWS Fundamentals

- [ ] What is AWS?
- [ ] Regions
- [ ] Availability Zones
- [ ] Edge locations
- [ ] AWS global infrastructure
- [ ] AWS accounts
- [ ] Root account
- [ ] IAM users
- [ ] IAM roles
- [ ] IAM policies
- [ ] AWS CLI
- [ ] AWS SDK
- [ ] AWS Console
- [ ] AWS pricing
- [ ] AWS Free Tier
- [ ] Billing
- [ ] Cost management

---

## 7. AWS IAM

- [ ] IAM
- [ ] User
- [ ] Group
- [ ] Role
- [ ] Policy
- [ ] Permission
- [ ] Resource-based policy
- [ ] Identity-based policy
- [ ] Trust policy
- [ ] Permission boundaries
- [ ] Least privilege
- [ ] MFA
- [ ] Access keys
- [ ] Temporary credentials
- [ ] IAM policy evaluation
- [ ] Cross-account access

### Practice

- [ ] Create IAM user
- [ ] Create IAM role
- [ ] Create custom policy
- [ ] Attach policy
- [ ] Assume role
- [ ] Use role with EC2
- [ ] Use role with GitHub Actions

---

## 8. AWS CLI

- [ ] Install AWS CLI
- [ ] Configure AWS CLI
- [ ] Profiles
- [ ] Credentials
- [ ] Regions
- [ ] Output formats
- [ ] AWS CLI commands
- [ ] JSON output
- [ ] CLI automation
- [ ] CLI scripting

---

## 9. EC2

- [ ] What is EC2?
- [ ] Instance
- [ ] AMI
- [ ] Instance types
- [ ] CPU
- [ ] Memory
- [ ] Storage
- [ ] Network
- [ ] On-demand instances
- [ ] Reserved/Savings concepts
- [ ] Spot instances
- [ ] Instance lifecycle
- [ ] Stop
- [ ] Start
- [ ] Reboot
- [ ] Terminate

### Practice

- [ ] Launch Ubuntu EC2
- [ ] Connect using SSH
- [ ] Configure server
- [ ] Install Node.js
- [ ] Deploy Node.js application
- [ ] Configure environment variables
- [ ] Configure firewall
- [ ] Attach domain
- [ ] Enable HTTPS
- [ ] Monitor server
- [ ] Restart application

---

## 10. EC2 Networking

- [ ] Public IP
- [ ] Private IP
- [ ] Elastic IP
- [ ] Security groups
- [ ] Inbound rules
- [ ] Outbound rules
- [ ] Network interfaces
- [ ] Ports
- [ ] SSH port
- [ ] HTTP port
- [ ] HTTPS port
- [ ] Custom application ports

---

## 11. SSH & Server Access

- [ ] SSH keys
- [ ] Key pairs
- [ ] Private key
- [ ] Public key
- [ ] `ssh`
- [ ] `scp`
- [ ] `rsync`
- [ ] SSH agent
- [ ] SSH hardening
- [ ] Disable password authentication
- [ ] Restrict SSH access
- [ ] Bastion concepts
- [ ] Session Manager concepts

---

## 12. EBS

- [ ] What is EBS?
- [ ] EBS volume
- [ ] Root volume
- [ ] Data volume
- [ ] Volume types
- [ ] IOPS
- [ ] Throughput
- [ ] Snapshots
- [ ] Resize volume
- [ ] Attach volume
- [ ] Detach volume
- [ ] Encryption
- [ ] Backup strategy

---

## 13. AMI

- [ ] What is AMI?
- [ ] Public AMI
- [ ] Private AMI
- [ ] Custom AMI
- [ ] Create AMI
- [ ] Launch instance from AMI
- [ ] AMI lifecycle
- [ ] Image versioning

---

## 14. S3

- [ ] What is S3?
- [ ] Bucket
- [ ] Object
- [ ] Key
- [ ] Region
- [ ] Object metadata
- [ ] Object storage
- [ ] Bucket policies
- [ ] IAM access
- [ ] Public access
- [ ] Block Public Access
- [ ] Object ownership
- [ ] Versioning
- [ ] Encryption
- [ ] Lifecycle rules

### Practice

- [ ] Create bucket
- [ ] Upload files
- [ ] Download files
- [ ] Delete files
- [ ] Configure permissions
- [ ] Upload from Node.js
- [ ] Generate presigned URLs
- [ ] Configure lifecycle
- [ ] Enable versioning

---

## 15. S3 Advanced

- [ ] Storage classes
- [ ] Standard
- [ ] Intelligent-Tiering
- [ ] Standard-IA
- [ ] One Zone-IA
- [ ] Glacier concepts
- [ ] Lifecycle transitions
- [ ] Multipart upload
- [ ] Object versioning
- [ ] Object Lock
- [ ] Replication
- [ ] Cross-region replication
- [ ] Event notifications

---

## 16. CloudFront

- [ ] What is CDN?
- [ ] What is CloudFront?
- [ ] Distribution
- [ ] Origin
- [ ] Edge location
- [ ] Cache behavior
- [ ] Cache policy
- [ ] Origin request policy
- [ ] TTL
- [ ] Cache invalidation
- [ ] HTTPS
- [ ] Custom domain
- [ ] S3 + CloudFront
- [ ] EC2 + CloudFront

---

## 17. Route 53

- [ ] What is Route 53?
- [ ] Hosted zone
- [ ] Public hosted zone
- [ ] Private hosted zone
- [ ] DNS records
- [ ] A record
- [ ] AAAA
- [ ] CNAME
- [ ] Alias record
- [ ] Health checks
- [ ] Routing policies

### Routing

- [ ] Simple routing
- [ ] Weighted routing
- [ ] Latency routing
- [ ] Failover routing
- [ ] Geolocation routing
- [ ] Geoproximity concepts

---

## 18. VPC

- [ ] What is VPC?
- [ ] CIDR
- [ ] Subnet
- [ ] Route table
- [ ] Internet Gateway
- [ ] NAT Gateway
- [ ] Security Group
- [ ] Network ACL
- [ ] Public subnet
- [ ] Private subnet
- [ ] Availability Zone
- [ ] VPC endpoints
- [ ] DNS inside VPC

---

## 19. VPC Architecture

```text
Internet
   |
   v
Internet Gateway
   |
   v
Public Subnet
   |
Load Balancer
   |
Private Subnet
   |
Application Servers
   |
Private Database
```

- [ ] Why database should usually be private
- [ ] Why application servers can be private
- [ ] Why load balancer can be public
- [ ] How outbound internet works
- [ ] NAT Gateway
- [ ] Routing tables
- [ ] Security groups
- [ ] Network ACLs

---

## 20. Security Groups

- [ ] Stateful firewall
- [ ] Inbound rules
- [ ] Outbound rules
- [ ] Port rules
- [ ] IP rules
- [ ] Security-group references
- [ ] Least privilege
- [ ] SSH restriction
- [ ] Application port restriction
- [ ] Database access restriction

---

## 21. Network ACL

- [ ] What is NACL?
- [ ] Stateless firewall
- [ ] Inbound rules
- [ ] Outbound rules
- [ ] Rule priority
- [ ] Allow rules
- [ ] Deny rules
- [ ] Security Group vs NACL

---

## 22. Load Balancing

- [ ] Why load balancer?
- [ ] Horizontal scaling
- [ ] Health checks
- [ ] Traffic distribution
- [ ] SSL termination
- [ ] High availability
- [ ] Application Load Balancer
- [ ] Network Load Balancer
- [ ] Gateway Load Balancer concepts

### ALB

- [ ] Listener
- [ ] Target group
- [ ] Target
- [ ] Health check
- [ ] Routing rules
- [ ] Path-based routing
- [ ] Host-based routing
- [ ] HTTPS listener

---

## 23. Auto Scaling

- [ ] What is Auto Scaling?
- [ ] Horizontal scaling
- [ ] Vertical scaling
- [ ] Auto Scaling Group
- [ ] Launch template
- [ ] Minimum instances
- [ ] Maximum instances
- [ ] Desired capacity
- [ ] Health checks
- [ ] Scaling policies

### Scaling Strategies

- [ ] Target tracking
- [ ] Step scaling
- [ ] Scheduled scaling
- [ ] Predictive scaling concepts

---

## 24. High Availability

- [ ] Single point of failure
- [ ] Redundancy
- [ ] Multiple Availability Zones
- [ ] Load balancing
- [ ] Auto Scaling
- [ ] Database redundancy
- [ ] Backup
- [ ] Disaster recovery

---

## 25. AWS RDS

- [ ] What is RDS?
- [ ] Managed database
- [ ] Database engine
- [ ] MySQL
- [ ] PostgreSQL
- [ ] MariaDB
- [ ] SQL Server
- [ ] Oracle concepts
- [ ] DB instance
- [ ] Storage
- [ ] Backups
- [ ] Snapshots
- [ ] Multi-AZ
- [ ] Read replicas
- [ ] Parameter groups
- [ ] Security groups
- [ ] Encryption

---

## 26. RDS Architecture

- [ ] Private database
- [ ] Application server access
- [ ] Database security group
- [ ] Multi-AZ
- [ ] Automated backups
- [ ] Point-in-time recovery
- [ ] Read replicas
- [ ] Failover

---

## 27. Database Deployment

- [ ] Deploy database
- [ ] Database migrations
- [ ] Migration versioning
- [ ] Production migrations
- [ ] Rollback strategy
- [ ] Backup before migration
- [ ] Connection pooling
- [ ] Connection limits
- [ ] Database credentials
- [ ] Secrets management

---

## 28. ElastiCache

- [ ] What is caching?
- [ ] Redis
- [ ] Memcached
- [ ] Cache-aside
- [ ] TTL
- [ ] Cache invalidation
- [ ] Cache eviction
- [ ] Session storage
- [ ] Rate limiting with Redis
- [ ] Distributed caching

---

## 29. AWS Lambda

- [ ] What is Lambda?
- [ ] Function
- [ ] Runtime
- [ ] Event
- [ ] Invocation
- [ ] Cold start
- [ ] Warm execution
- [ ] Timeout
- [ ] Memory
- [ ] Concurrency
- [ ] Environment variables
- [ ] IAM execution role

---

## 30. Lambda Architecture

- [ ] API Gateway + Lambda
- [ ] S3 + Lambda
- [ ] EventBridge + Lambda
- [ ] SQS + Lambda
- [ ] Scheduled Lambda
- [ ] Async invocation
- [ ] Error handling
- [ ] Dead-letter concepts

---

## 31. API Gateway

- [ ] What is API Gateway?
- [ ] HTTP API
- [ ] REST API
- [ ] Routes
- [ ] Stages
- [ ] Authorizers
- [ ] Rate limiting
- [ ] Throttling
- [ ] CORS
- [ ] API keys
- [ ] Usage plans
- [ ] Lambda integration

---

## 32. ECS

- [ ] What is ECS?
- [ ] Cluster
- [ ] Service
- [ ] Task
- [ ] Task definition
- [ ] Container
- [ ] Fargate
- [ ] ECS on EC2
- [ ] Service discovery
- [ ] Load balancer integration
- [ ] Auto scaling

---

## 33. Docker for Deployment

- [ ] What is Docker?
- [ ] Image
- [ ] Container
- [ ] Dockerfile
- [ ] Docker Compose
- [ ] Container networking
- [ ] Container volumes
- [ ] Environment variables
- [ ] Docker registry
- [ ] Image tags

### Production Docker

- [ ] Multi-stage builds
- [ ] Small images
- [ ] Non-root user
- [ ] Health checks
- [ ] Resource limits
- [ ] Secure secrets
- [ ] Image scanning

---

## 34. ECR

- [ ] What is ECR?
- [ ] Repository
- [ ] Image
- [ ] Push image
- [ ] Pull image
- [ ] Image tags
- [ ] Image lifecycle
- [ ] Image scanning
- [ ] Private registry

---

## 35. ECS + Fargate Deployment

```text
Developer
   |
   v
GitHub
   |
   v
CI/CD
   |
   v
Docker Build
   |
   v
ECR
   |
   v
ECS / Fargate
   |
   v
Application Load Balancer
   |
   v
Users
```

- [ ] Dockerize Node.js app
- [ ] Push image to ECR
- [ ] Create ECS cluster
- [ ] Create task definition
- [ ] Create ECS service
- [ ] Attach ALB
- [ ] Configure security groups
- [ ] Configure environment variables
- [ ] Deploy
- [ ] Scale

---

## 36. AWS Secrets Manager

- [ ] What is Secrets Manager?
- [ ] Store secrets
- [ ] Retrieve secrets
- [ ] IAM permissions
- [ ] Secret rotation
- [ ] Database credentials
- [ ] API keys
- [ ] Application secrets

---

## 37. AWS Systems Manager Parameter Store

- [ ] Parameters
- [ ] SecureString
- [ ] Configuration management
- [ ] Secrets
- [ ] IAM permissions
- [ ] Parameter versioning
- [ ] Parameter Store vs Secrets Manager

---

## 38. AWS KMS

- [ ] What is KMS?
- [ ] Encryption keys
- [ ] Customer-managed keys
- [ ] AWS-managed keys
- [ ] Key policies
- [ ] Key rotation
- [ ] Encryption/decryption
- [ ] Envelope encryption
- [ ] IAM + KMS

---

## 39. Monitoring

- [ ] What is observability?
- [ ] Logs
- [ ] Metrics
- [ ] Traces
- [ ] Monitoring
- [ ] Alerting

---

## 40. CloudWatch

- [ ] CloudWatch
- [ ] Metrics
- [ ] Logs
- [ ] Log groups
- [ ] Log streams
- [ ] Alarms
- [ ] Dashboards
- [ ] Events
- [ ] Agent
- [ ] Custom metrics

### Monitor

- [ ] CPU
- [ ] Memory
- [ ] Disk
- [ ] Network
- [ ] Request count
- [ ] Error rate
- [ ] Latency
- [ ] Database metrics

---

## 41. AWS CloudTrail

- [ ] What is CloudTrail?
- [ ] API activity
- [ ] User activity
- [ ] Audit trail
- [ ] Security monitoring
- [ ] Event history
- [ ] Log storage
- [ ] Compliance concepts

---

## 42. Application Logging

- [ ] Structured logging
- [ ] JSON logs
- [ ] Log levels
- [ ] Error logs
- [ ] Access logs
- [ ] Security logs
- [ ] Request IDs
- [ ] Correlation IDs
- [ ] Log rotation
- [ ] Log retention

---

## 43. Application Monitoring

- [ ] Health endpoint
- [ ] Readiness
- [ ] Liveness
- [ ] Error rate
- [ ] Latency
- [ ] Throughput
- [ ] CPU usage
- [ ] Memory usage
- [ ] Database connections
- [ ] Queue depth

---

## 44. AWS X-Ray / Distributed Tracing

- [ ] Distributed tracing
- [ ] Trace
- [ ] Span
- [ ] Service map
- [ ] Request tracing
- [ ] Database tracing
- [ ] External API tracing
- [ ] Debug latency

---

## 45. CI/CD Fundamentals

- [ ] What is CI?
- [ ] What is CD?
- [ ] Continuous integration
- [ ] Continuous delivery
- [ ] Continuous deployment
- [ ] Build pipeline
- [ ] Test pipeline
- [ ] Deployment pipeline
- [ ] Rollback
- [ ] Artifacts

---

## 46. GitHub Actions

- [ ] Workflow
- [ ] Trigger
- [ ] Job
- [ ] Step
- [ ] Runner
- [ ] Secrets
- [ ] Environment
- [ ] Artifacts
- [ ] Cache
- [ ] Matrix builds

### Build

- [ ] Run tests
- [ ] Run lint
- [ ] Build application
- [ ] Build Docker image
- [ ] Push image to ECR
- [ ] Deploy to EC2
- [ ] Deploy to ECS

---

## 47. EC2 CI/CD

```text
GitHub
   ↓
GitHub Actions
   ↓
Build/Test
   ↓
SSH / Deployment mechanism
   ↓
EC2
   ↓
Restart application
```

- [ ] Automated deployment
- [ ] SSH deployment
- [ ] Git-based deployment
- [ ] Artifact deployment
- [ ] Environment variables
- [ ] Rollback
- [ ] Zero downtime

---

## 48. ECS CI/CD

```text
GitHub
   ↓
GitHub Actions
   ↓
Docker Build
   ↓
ECR
   ↓
ECS
   ↓
New Task Definition
   ↓
Rolling Deployment
```

- [ ] Build image
- [ ] Tag image
- [ ] Push image
- [ ] Update task definition
- [ ] Deploy service
- [ ] Health check
- [ ] Rollback

---

## 49. Infrastructure as Code

- [ ] What is IaC?
- [ ] Why IaC?
- [ ] Reproducible infrastructure
- [ ] Infrastructure version control
- [ ] Terraform
- [ ] AWS CloudFormation
- [ ] AWS CDK

### Terraform

- [ ] Providers
- [ ] Resources
- [ ] Variables
- [ ] Outputs
- [ ] Modules
- [ ] State
- [ ] Remote state
- [ ] State locking
- [ ] `terraform init`
- [ ] `terraform plan`
- [ ] `terraform apply`
- [ ] `terraform destroy`

---

## 50. AWS CDK

- [ ] What is CDK?
- [ ] Constructs
- [ ] Stacks
- [ ] Applications
- [ ] Infrastructure using TypeScript
- [ ] Synth
- [ ] Deploy
- [ ] CloudFormation underneath

---

## 51. Terraform AWS Deployment Project

```text
VPC
├── Public Subnets
│   └── Load Balancer
│
├── Private Subnets
│   ├── EC2 / ECS
│   └── RDS
│
└── NAT Gateway
```

- [ ] Create VPC
- [ ] Create subnets
- [ ] Create route tables
- [ ] Create security groups
- [ ] Create ALB
- [ ] Create EC2/ECS
- [ ] Create RDS
- [ ] Create S3
- [ ] Create IAM roles
- [ ] Deploy using Terraform

---

## 52. Deployment Strategies

- [ ] Recreate deployment
- [ ] Rolling deployment
- [ ] Blue-green deployment
- [ ] Canary deployment
- [ ] A/B deployment
- [ ] Shadow deployment concepts

### Understand

- [ ] Downtime
- [ ] Rollback
- [ ] Infrastructure cost
- [ ] Risk
- [ ] Traffic shifting

---

## 53. Zero-Downtime Deployment

- [ ] Health checks
- [ ] Load balancer
- [ ] Multiple instances
- [ ] Rolling updates
- [ ] Graceful shutdown
- [ ] Connection draining
- [ ] Backward-compatible APIs
- [ ] Database migration compatibility

---

## 54. Database Migration Deployment

- [ ] Schema migration
- [ ] Backward-compatible migration
- [ ] Expand-and-contract pattern
- [ ] Migration ordering
- [ ] Rollback limitations
- [ ] Data migration
- [ ] Migration testing
- [ ] Production migration safety

---

## 55. Application Configuration

- [ ] Environment variables
- [ ] Configuration files
- [ ] Runtime configuration
- [ ] Build-time configuration
- [ ] Secrets
- [ ] Feature flags
- [ ] Configuration validation
- [ ] Configuration versioning

---

## 56. Health Checks

- [ ] Liveness
- [ ] Readiness
- [ ] Startup
- [ ] Dependency health
- [ ] Database health
- [ ] Redis health
- [ ] External API health

### Implement

- [ ] `/health`
- [ ] `/ready`
- [ ] Graceful shutdown

---

## 57. Reverse Proxy

- [ ] What is reverse proxy?
- [ ] Nginx
- [ ] Proxying
- [ ] Static files
- [ ] SSL termination
- [ ] HTTP → HTTPS
- [ ] Domain routing
- [ ] Load balancing
- [ ] Rate limiting
- [ ] Compression
- [ ] Security headers

---

## 58. Node.js Production Deployment

- [ ] Production environment
- [ ] `NODE_ENV`
- [ ] Process management
- [ ] Graceful shutdown
- [ ] Error handling
- [ ] Logging
- [ ] Health checks
- [ ] Environment variables
- [ ] Secrets
- [ ] Reverse proxy
- [ ] HTTPS
- [ ] Monitoring

### Process Managers

- [ ] systemd
- [ ] PM2
- [ ] Understand when to use each

---

## 59. Scaling

### Vertical Scaling

- [ ] Increase CPU
- [ ] Increase RAM
- [ ] Bigger instance

### Horizontal Scaling

- [ ] Multiple instances
- [ ] Load balancer
- [ ] Auto Scaling
- [ ] Stateless applications
- [ ] Shared session storage
- [ ] Shared file storage

---

## 60. Stateless Architecture

- [ ] What is stateless?
- [ ] Why stateless?
- [ ] Session problem
- [ ] Shared Redis sessions
- [ ] JWT considerations
- [ ] Shared file storage
- [ ] Externalized state

---

## 61. Caching

- [ ] Browser cache
- [ ] CDN cache
- [ ] Application cache
- [ ] Redis
- [ ] Database cache
- [ ] Cache invalidation
- [ ] TTL
- [ ] Cache-aside
- [ ] Write-through
- [ ] Write-back concepts

---

## 62. Message Queues

- [ ] Why queues?
- [ ] Producer
- [ ] Consumer
- [ ] Message
- [ ] Queue
- [ ] Visibility timeout
- [ ] Retry
- [ ] Dead-letter queue
- [ ] Idempotent consumers

### AWS

- [ ] SQS
- [ ] SNS
- [ ] EventBridge

---

## 63. SQS

- [ ] Standard queue
- [ ] FIFO queue
- [ ] Visibility timeout
- [ ] Message retention
- [ ] Dead-letter queue
- [ ] Long polling
- [ ] Retry
- [ ] Consumer scaling

---

## 64. SNS

- [ ] Pub/Sub
- [ ] Topic
- [ ] Subscriber
- [ ] Fan-out
- [ ] Message delivery
- [ ] SNS + SQS

---

## 65. Event-Driven Architecture

- [ ] Event
- [ ] Producer
- [ ] Consumer
- [ ] Event bus
- [ ] Event-driven architecture
- [ ] Async processing
- [ ] Eventual consistency
- [ ] Retry
- [ ] Idempotency
- [ ] Dead-letter handling

---

## 66. AWS EventBridge

- [ ] Event bus
- [ ] Rules
- [ ] Targets
- [ ] Event patterns
- [ ] Scheduled events
- [ ] Custom events
- [ ] Service events

---

## 67. AWS SES

- [ ] Email service concepts
- [ ] Verified identity
- [ ] Domain verification
- [ ] SMTP
- [ ] API sending
- [ ] Email templates
- [ ] Bounce handling
- [ ] Complaint handling
- [ ] Reputation

---

## 68. AWS CloudFront + S3 Frontend

```text
User
  ↓
Route 53
  ↓
CloudFront
  ↓
S3
```

- [ ] Build frontend
- [ ] Upload build to S3
- [ ] Configure CloudFront
- [ ] Custom domain
- [ ] HTTPS
- [ ] Cache invalidation
- [ ] SPA routing

---

## 69. Full-Stack AWS Architecture

```text
                    Internet
                       |
                    Route 53
                       |
                  CloudFront
                  /         \
                 /           \
              S3             ALB
           Frontend           |
                              |
                         ECS / EC2
                              |
                    ------------------
                    |                |
                   RDS             Redis
                    |
                  Backup
```

- [ ] Frontend deployment
- [ ] Backend deployment
- [ ] Database deployment
- [ ] Cache
- [ ] DNS
- [ ] HTTPS
- [ ] Load balancing
- [ ] Monitoring
- [ ] CI/CD

---

## 70. Production Security

- [ ] IAM least privilege
- [ ] MFA
- [ ] No root access for daily work
- [ ] SSH security
- [ ] Security groups
- [ ] Private databases
- [ ] HTTPS
- [ ] Secrets Manager
- [ ] KMS
- [ ] Encryption at rest
- [ ] Encryption in transit
- [ ] CloudTrail
- [ ] Security monitoring
- [ ] Dependency scanning
- [ ] Container scanning
- [ ] Backup strategy

---

## 71. AWS Backup & Disaster Recovery

- [ ] Backup strategy
- [ ] EBS snapshots
- [ ] RDS backups
- [ ] S3 versioning
- [ ] Cross-region replication
- [ ] Recovery Point Objective
- [ ] Recovery Time Objective
- [ ] Disaster recovery
- [ ] Failover
- [ ] Restore testing

### DR Strategies

- [ ] Backup and restore
- [ ] Pilot light
- [ ] Warm standby
- [ ] Multi-site active/active

---

## 72. AWS Cost Optimization

- [ ] AWS pricing model
- [ ] EC2 pricing
- [ ] EBS pricing
- [ ] S3 pricing
- [ ] Data transfer pricing
- [ ] NAT Gateway costs
- [ ] Load balancer costs
- [ ] RDS costs
- [ ] CloudFront costs
- [ ] Lambda pricing
- [ ] Cost Explorer
- [ ] Budgets
- [ ] Billing alerts
- [ ] Right-sizing
- [ ] Reserved capacity concepts
- [ ] Savings Plans
- [ ] Spot instances

---

## 73. AWS Organizations

- [ ] Organizations
- [ ] Management account
- [ ] Member accounts
- [ ] Organizational Units
- [ ] Service Control Policies
- [ ] Multi-account strategy
- [ ] Account isolation
- [ ] Centralized billing

---

## 74. AWS Well-Architected Framework

Learn all six pillars:

- [ ] Operational Excellence
- [ ] Security
- [ ] Reliability
- [ ] Performance Efficiency
- [ ] Cost Optimization
- [ ] Sustainability

---

## 75. Reliability Engineering

- [ ] Availability
- [ ] Reliability
- [ ] Fault tolerance
- [ ] Redundancy
- [ ] Failure domains
- [ ] Health checks
- [ ] Auto recovery
- [ ] Graceful degradation
- [ ] Retry strategies
- [ ] Circuit breakers
- [ ] Timeouts
- [ ] Backpressure

---

## 76. Observability

- [ ] Logs
- [ ] Metrics
- [ ] Traces
- [ ] Correlation IDs
- [ ] Distributed tracing
- [ ] Dashboards
- [ ] Alerts
- [ ] SLO
- [ ] SLA
- [ ] SLI
- [ ] Error budget

---

## 77. Performance & Capacity Planning

- [ ] Load testing
- [ ] Stress testing
- [ ] Benchmarking
- [ ] CPU bottlenecks
- [ ] Memory bottlenecks
- [ ] Network bottlenecks
- [ ] Database bottlenecks
- [ ] Connection limits
- [ ] Throughput
- [ ] Latency
- [ ] Capacity planning

---

## 78. Kubernetes — Optional Advanced Track

- [ ] What is Kubernetes?
- [ ] Cluster
- [ ] Node
- [ ] Pod
- [ ] Deployment
- [ ] Service
- [ ] Ingress
- [ ] ConfigMap
- [ ] Secret
- [ ] Namespace
- [ ] ReplicaSet
- [ ] StatefulSet
- [ ] DaemonSet
- [ ] Job
- [ ] CronJob
- [ ] Horizontal Pod Autoscaler
- [ ] Persistent Volume
- [ ] Persistent Volume Claim
- [ ] Kubernetes networking
- [ ] Kubernetes security

### AWS

- [ ] EKS
- [ ] EKS node groups
- [ ] Fargate concepts
- [ ] Load balancer integration
- [ ] IAM integration

---

## 79. Infrastructure as Code Project

Build your entire infrastructure from code:

- [ ] VPC
- [ ] Public subnets
- [ ] Private subnets
- [ ] Internet Gateway
- [ ] NAT Gateway
- [ ] Route tables
- [ ] Security groups
- [ ] ALB
- [ ] ECS/EC2
- [ ] RDS
- [ ] S3
- [ ] IAM roles
- [ ] CloudWatch
- [ ] Route 53
- [ ] Destroy infrastructure
- [ ] Recreate infrastructure
- [ ] Version infrastructure
- [ ] Review infrastructure changes

---

## 80. Production Deployment Project

Build a real production-style backend:

```text
                         Users
                           |
                       Route 53
                           |
                       CloudFront
                           |
                         ALB
                           |
                 ---------------------
                 |                   |
              ECS/EC2             ECS/EC2
                 |                   |
                 ----------- ----------
                           |
                         Redis
                           |
                          RDS
                           |
                         Backup
```

Supporting services:

```text
GitHub
   |
GitHub Actions
   |
Docker
   |
ECR
   |
ECS
```

And:

```text
CloudWatch → Logs + Metrics + Alerts
CloudTrail  → Audit
Secrets Manager → Secrets
KMS → Encryption
S3 → Files/Backups
```

---

# Final Deployment Mastery Checklist

- [ ] I understand deployment
- [ ] I understand Linux servers
- [ ] I understand networking
- [ ] I understand DNS
- [ ] I understand HTTP/HTTPS
- [ ] I understand AWS Regions
- [ ] I understand Availability Zones
- [ ] I understand IAM
- [ ] I can use AWS CLI
- [ ] I can launch EC2
- [ ] I can SSH into EC2
- [ ] I can deploy Node.js to EC2
- [ ] I understand EBS
- [ ] I understand AMIs
- [ ] I understand S3
- [ ] I can upload files to S3
- [ ] I understand CloudFront
- [ ] I understand Route 53
- [ ] I understand VPC
- [ ] I understand public/private subnets
- [ ] I understand Security Groups
- [ ] I understand NACLs
- [ ] I understand NAT Gateway
- [ ] I can configure an ALB
- [ ] I understand Auto Scaling
- [ ] I understand RDS
- [ ] I understand Redis/ElastiCache
- [ ] I understand Lambda
- [ ] I understand API Gateway
- [ ] I understand Docker
- [ ] I can Dockerize a Node.js app
- [ ] I understand ECR
- [ ] I understand ECS
- [ ] I understand Fargate
- [ ] I can deploy Docker containers to ECS
- [ ] I understand Secrets Manager
- [ ] I understand KMS
- [ ] I understand CloudWatch
- [ ] I understand CloudTrail
- [ ] I understand CI/CD
- [ ] I can build GitHub Actions pipelines
- [ ] I understand Infrastructure as Code
- [ ] I can use Terraform
- [ ] I understand deployment strategies
- [ ] I can perform zero-downtime deployments
- [ ] I understand database migrations in production
- [ ] I understand horizontal scaling
- [ ] I understand stateless architecture
- [ ] I understand caching
- [ ] I understand queues
- [ ] I understand event-driven architecture
- [ ] I understand backups
- [ ] I understand disaster recovery
- [ ] I understand cloud security
- [ ] I understand cost optimization
- [ ] I understand observability
- [ ] I understand reliability
- [ ] I can troubleshoot production failures
- [ ] I can deploy a production-grade backend
- [ ] I can reproduce infrastructure from code

---

# Recommended Learning Order

1. Linux + Terminal
2. Networking Fundamentals
3. DNS + HTTP/HTTPS
4. AWS Fundamentals + IAM
5. EC2
6. SSH + Linux Server Deployment
7. Nginx + Domain + HTTPS
8. S3
9. Route 53
10. VPC + Subnets + Security Groups + NAT
11. RDS
12. ALB
13. Auto Scaling
14. CloudWatch + CloudTrail
15. Docker
16. ECR
17. ECS + Fargate
18. SQS + SNS + EventBridge
19. Redis / ElastiCache
20. Secrets Manager + KMS
21. GitHub Actions + CI/CD
22. Terraform / IaC
23. Zero-downtime deployments
24. High Availability + Disaster Recovery
25. Cost Optimization
26. Observability + Reliability
27. Kubernetes/EKS (optional advanced)

---

# Practical Project Progression

## Project 1 — Basic EC2 Deployment

**Node.js → Ubuntu EC2 → Nginx → Domain → HTTPS**

- [ ] Deploy Node.js app
- [ ] Configure Nginx
- [ ] Connect domain
- [ ] Enable HTTPS
- [ ] Configure process management
- [ ] Add health checks

## Project 2 — Full-Stack AWS Basics

**Node.js + RDS + S3 + Route 53**

- [ ] Backend
- [ ] Database
- [ ] File storage
- [ ] Domain
- [ ] HTTPS

## Project 3 — Highly Available EC2 Architecture

**VPC → Public/Private Subnets → ALB → EC2 Auto Scaling → RDS**

- [ ] Multi-AZ
- [ ] Load balancing
- [ ] Auto Scaling
- [ ] Private database
- [ ] Monitoring

## Project 4 — Containerized Deployment

**Docker → ECR → ECS Fargate → ALB → RDS**

- [ ] Dockerize application
- [ ] Push image to ECR
- [ ] Deploy to ECS
- [ ] Configure ALB
- [ ] Connect RDS
- [ ] Scale service

## Project 5 — Automated CI/CD

**GitHub → GitHub Actions → Docker → ECR → ECS**

- [ ] Automated tests
- [ ] Build Docker image
- [ ] Push to ECR
- [ ] Deploy to ECS
- [ ] Health checks
- [ ] Rollback

## Project 6 — Infrastructure as Code

**Terraform → Entire Project 5 Infrastructure**

- [ ] VPC
- [ ] Subnets
- [ ] Security groups
- [ ] ALB
- [ ] ECS
- [ ] ECR
- [ ] RDS
- [ ] IAM
- [ ] CloudWatch
- [ ] Route 53

## Project 7 — Production Architecture

Build a production-style system with:

- [ ] Multi-AZ
- [ ] Auto Scaling
- [ ] Redis
- [ ] SQS
- [ ] CloudWatch
- [ ] Secrets Manager
- [ ] KMS
- [ ] Backups
- [ ] Monitoring
- [ ] Zero-downtime deployment
- [ ] Disaster recovery
- [ ] Infrastructure as Code
