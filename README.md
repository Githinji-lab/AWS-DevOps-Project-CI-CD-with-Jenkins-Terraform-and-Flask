🚀 AWS DevOps Project: CI/CD with Jenkins, Terraform, and Flask
This project automates the deployment of a Python Flask REST API using Jenkins, Terraform, and AWS services. It follows Infrastructure as Code (IaC) principles with Terraform and sets up a CI/CD pipeline using Jenkins to deploy the application on AWS.

📌 Overview
✅ Terraform provisions AWS infrastructure (EC2, RDS, Load Balancer, Route 53, IAM, Security Groups)
✅ Jenkins manages the CI/CD pipeline, automating the deployment of the Flask app
✅ Flask App is deployed with MySQL RDS as the backend
✅ AWS Load Balancer & Route 53 ensure scalability & secure HTTPS access

📂 Project Structure
graphql
Copy
Edit
aws-devops-project/
│── terraform-infra/    # Terraform scripts for AWS setup
│── jenkins-ci-cd/      # Jenkins pipeline & configuration
│── flask-app/          # Python Flask REST API
│── images/             # Project workflow diagrams
│── README.md           # Project documentation
📷 Workflow Diagram
(Make sure your workflow diagram is saved in the images/ folder.)

markdown
Copy
Edit
![Workflow Diagram](images/workflow-diagram.png)
🛠️ Tools & Technologies Used
✅ AWS (EC2, RDS, Route 53, Load Balancer, ACM)
✅ Terraform for Infrastructure as Code
✅ Jenkins for CI/CD
✅ Python Flask for REST API
✅ MySQL RDS for database

🔧 How to Set Up the Project
1️⃣ Clone the Repo
sh
Copy
Edit
git clone https://github.com/yourusername/aws-devops-project.git
cd aws-devops-project
2️⃣ Deploy Infrastructure with Terraform
sh
Copy
Edit
cd terraform-infra
terraform init
terraform apply -auto-approve
This will set up the EC2 instance, security groups, RDS database, and networking (VPC, subnets, Route 53).

3️⃣ Configure Jenkins for CI/CD
Install Jenkins on the provisioned EC2 instance
Set up a GitHub webhook to trigger deployments
Configure the Jenkins pipeline for automatic deployment
4️⃣ Deploy Flask App
Push code changes to GitHub
Jenkins will automatically pull and deploy the Flask app on EC2
Access the app via the Load Balancer URL
⚠️ Challenges & Solutions
Challenge	Solution
Permission denied on SSH key when trying to SSH into EC2	Manually imported the existing key pair into Terraform instead of creating a duplicate
Jenkins GitHub Webhook not triggering builds	Configured proper webhook settings and adjusted security group rules
IAM permissions preventing Jenkins from accessing AWS resources	Created an IAM role with correct policies for Jenkins
Terraform InvalidKeyPair.Duplicate error	Used terraform import to track the existing key instead of trying to recreate it
Load Balancer not resolving Route 53 domain	Debugged ACM SSL certificate validation and ensured DNS propagation
📎 References & Credits
This project was inspired by @RahulWagh’s tutorial. Big thanks for the insightful guide! 🙌

📌 Next Steps & Improvements
🚀 Containerize the Flask App using Docker
🚀 Deploy with Kubernetes (EKS) for better scaling
🚀 Enhance security with IAM best practices & AWS Secrets Manager

💡 Contributing
If you’d like to contribute or suggest improvements, feel free to open an issue or submit a pull request!
