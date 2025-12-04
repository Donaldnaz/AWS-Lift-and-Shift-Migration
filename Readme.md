# **Lift & Shift Application Workload on AWS Cloud**

This project demonstrates how I migrated the **Profile multi-tier application** from an on-premises/VM-based setup to the **AWS cloud** using a **Lift and Shift strategy**.  
Instead of re-architecting, the existing stack was replicated in AWS, showing how businesses can move workloads quickly while still gaining **scalability**, **flexibility**, and **cost efficiency**.

- **AWS Lift & Shift Project** → [`lift & shift`](https://anasiezeikenna.notion.site/Lift-Shift-Application-Workload-on-AWS-Cloud-26105c74585e804c9eece9459b8f214d)


### **Overview**

### **AWS Services Used**

- **Compute:** Amazon EC2 (Tomcat, RabbitMQ, Memcache, MySQL)  
- **Networking & Routing:** Elastic Load Balancer (HTTPS), Route 53 (Private DNS)  
- **Scalability:** Auto Scaling Groups  
- **Storage:** Amazon S3 (artifacts), Amazon EFS/EBS (persistent storage)  
- **Security & Management:** IAM, Security Groups, ACM for SSL/TLS  



### **Architecture Overview**

<img width="3840" height="2160" alt="image" src="https://github.com/user-attachments/assets/56f35f84-684b-4dd7-9f67-0ff77da1955d" />

Running the full **Profile** stack on AWS costs approximately **$47.68/month**, proving how cloud migration enables **reliability and elasticity** at a fraction of traditional on-premise costs.

### **Workflow**

1. Users connect via **HTTPS** through an **Application Load Balancer**, secured with **ACM certificates**.  
2. Requests are routed to **Tomcat servers** within an **Auto Scaling Group**.  
3. Backend services (**MySQL, RabbitMQ, Memcache**) run on private EC2 instances managed with **Route 53 private DNS**.  
4. Application artifacts are deployed from **Amazon S3** onto Tomcat servers.  
5. Each layer (frontend, app, backend) is isolated using **dedicated Security Groups**.


### **Why Lift & Shift**

Most enterprises still run legacy workloads in data centers, leading to:
- Slow and manual scaling  
- High infrastructure costs  
- Complex maintenance  

By **lifting and shifting** the iProfile stack to AWS, I demonstrated how to achieve:
- **Elastic scaling**  
- **Reduced costs** (CapEx → OpEx)  
- **Simplified operations**  

### **Implementation Steps**

- Analyzed the existing Profile stack (Tomcat, MySQL, RabbitMQ, Memcache, Nginx)  
- Designed equivalent AWS architecture with EC2, ELB, Route 53, and S3  
- Created **Security Groups** for each tier  
- Automated EC2 instance setup using **User Data scripts**  
- Deployed application artifacts from **S3 to Tomcat**  
- Configured **HTTPS** with ACM and **Load Balancer integration**  
- Implemented **Auto Scaling** for elasticity under variable traffic  
- Verified **DNS mapping** via **GoDaddy → ALB endpoint**

### **Setup & Configuration**

#### **1. Provisioning Infrastructure**
Created Security Groups and EC2 instances for Tomcat (Auto Scaling Group), MySQL, RabbitMQ, and Memcache.

#### **2. Deploying Artifacts**
Uploaded application build artifacts to **S3** and deployed them onto Tomcat servers automatically.

#### **3. Configuring Load Balancer**
Set up **ALB with ACM certificate** for secure HTTPS traffic.

#### **4. DNS Mapping**
Mapped **GoDaddy domain** to the **ALB DNS name**.

#### **5. Verifying Database Connectivity**
Confirmed MySQL connections and validated cross-service communication between app layers.


### **Project Highlights**

⚡ Demonstrates my ability to:
- Migrate real-world workloads to AWS  
- Design scalable, secure cloud architectures  
- Automate provisioning and deployment pipelines  
- Balance performance, cost, and maintainability in production-ready environments  

