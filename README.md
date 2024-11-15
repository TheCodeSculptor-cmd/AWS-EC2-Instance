# AWS EC2 Static Website Deployment

This project demonstrates how to set up a Linux server on AWS EC2, deploy a simple static website, and push the changes to GitHub.

## Project URL
This is a local Docker project from the roadmap.sh. You can find the project details. [here](https://roadmap.sh/projects/ec2-instance)

## Requirements

- AWS account
- GitHub account
- Basic knowledge of Linux, SSH, and Git
## Steps to Set Up
1. **Create an AWS Account**  
   If you don't already have an AWS account, go to [AWS](https://aws.amazon.com) and sign up for a free account.

2. **Launch an EC2 Instance**  
   - Use the **Ubuntu Server AMI**.
   - Choose **t2.micro** instance type (eligible for AWS Free Tier).
   - Use the default VPC and subnet for your region.
   - Configure the security group to allow inbound traffic on ports **22 (SSH)** and **80 (HTTP)**.
   - Create a key pair or use an existing one for SSH access.
   - Assign a public IP address to your instance.
  
3. **Connect to Your EC2 Instance**  
   - Use SSH to connect to your instance using the private key you generated.
   - Example SSH command:
     ```bash
     ssh -i your-key-pair.pem ubuntu@your-ec2-public-ip
     ```
4. **Install Web Server**  
   - Update your system and install Nginx:
     ```bash
     sudo apt update
     sudo apt install nginx
     ```

5. **Create and Deploy Static Website**  
   - Navigate to the Nginx web server directory:
     ```bash
     cd /var/www/html
     ```
   - Create a simple `index.html` file:
     ```bash
     echo "<h1>Welcome to My Static Website!</h1>" > index.html
     ```
   - Ensure the correct file permissions:
     ```bash
     sudo chown -R www-data:www-data /var/www/html
     ```

  6. **Access Your Website**  
   - Open your web browser and enter your EC2 instance's public IP address:
     ```
     http://your-ec2-public-ip
     ```


## Pushing the Project to GitHub

1. **Initialize Git Repository**  
   - Navigate to the project folder and initialize a Git repository:
     ```bash
     git init
     ```

2. **Add Your Files**  
   - Add all files to Git:
     ```bash
     git add .
     ```

3. **Commit Your Changes**  
   - Commit your files:
     ```bash
     git commit -m "Initial commit"
     ```

4. **Create a Remote Repository on GitHub**  
   - Create a new repository on GitHub and copy the URL.

5. **Push to GitHub**  
   - Add the remote repository and push your local changes:
     ```bash
     git remote add origin https://github.com/your-username/your-repo-name.git
     git push -u origin main
     ```

## Learning Outcomes
By completing this project, you will have gained hands-on experience with:

- Setting up EC2 instances on AWS
- Installing and configuring Nginx on a Linux server
- Deploying static websites to a cloud server
- Using Git for version control and pushing changes to GitHub




