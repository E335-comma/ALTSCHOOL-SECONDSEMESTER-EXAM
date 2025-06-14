# ALTSCHOOL SECOND SEMESTER EXAMINATION PROJECT

- NAME: Aderoju Elizabeth Ifeoluwa
- SCHOOL: Altschool Africa
- SCHOOL ID: ALT/SOE/024/5075
- BATCH: Tinyuka'24

---

# This is my Documentation for my Altschool Second Semester Examination Project

---

# My Project Overview

## The examination is basically about:
- Provisioning a server which I did with AWS(Elastic Compute Cloud).

- Setting up a web server in which I used Nginx instead of Apache because it is lightweight.

- Creation of a Dynamic Landing Page. 

- Networking & Security by allowing HTTP (Port 80) and HTTPS (Port 443).

---

# Objectives

The goal of my project is to provision a server using EC2, set up a web server, create a dynamic landing page, deploy the created dynamic landing page and necessary networking settings and security to make the landing page accessible to everyone and making sure it's secure enough to be accessed.

---

# Below is the step by step explanation on how I carried out the project:

---

## Step 1: Creating a Dynamic Landing Page

1. I created a personalized landing page showing information about me and a short pitch that explained why my project titled "AI Tune: The Future of Instrument Learning" innovative. I used a little bit of CSS animations for my page.
I created three files for my landing page and the three files are;


- index.html: It contains my HTML for my landing page.

- index.css: It contains my CSS codes with the animations and styling of my landing page.

---

## Step 2: Provisioning a server using AWS EC2

1. I chose AWS as my cloud provider

2. After I chose AWS as my cloud provider, I went ahead to log in to my AWS console, I checked my dashboard to launch an EC2 instance in which I saw some steps to take before launching the instance and the steps are:

- Names and Tags: I named it "My server"

- AMI (Amazon Machine Image): I chose Ubuntu Server 24.04 LTS because I feel more comfortable using Ubuntu server

- I created a new key pair with the name "project-server" which I later used to ssh into my EC2 instance.

I went straight to launching the EC2 because I forgot to setup my network but my instance was unable to launch, and this made me remember that I haven't setup my network. So I scrolled back to set my network.

- Network Settings

    - VPC: Default VPC

    - Subnet: I set it to a default subnet in any availability zone

    - Auto-assign public IP: Enable

    - Firewall(Security groups): 
        - I added a new security and;
            - I allowed HTTP which is on port 80 from any  IP address on the internet
            - I allowed SSH from only my PC address for security reason
            - Lastly, I allowed HTTPS which is on port 443 from any IP address on the internet

After I succesfully carried out these steps, I clicked on launch instance to create my EC2 instance which was successful.

---

## Step 3: Securing a Subdomain from FreeDNS for configuration of HTTPS

I got my subdomain from https://freedns.afraid.org/ . FreeDNS provides free third-party domain support, covers DNS during domain transfers and it offers services such as dynamic DNS hosting, static DNS hosting, and subdomain and domain hosting. It helps users to control their domain name traffic and  access their computers using a name instaed of a numeric IP address. When I got to the website I signed up, went ahead to create a subdomain, I input my EC2 Ip address as the destination, I chose a domain and I secured a domain with the name Adeife08.jumpingcrab.com

---

## Step 4: Installing Nginx and Securing Certbot 

I ssh into my EC2 instance using the key pair name that I created when trying to launch the instance and the key pair name is "project-server.pem" . I ssh into my instance by using the command "ssh -i .\project-server.pem ubuntu@16.171.28.67.
After I've successfully done that, I went on to taking the following steps:
    
- Upgrade and Update packages in the server by using command "sudo apt update && upgrade -y"

- Install Nginx
    - Command: sudo apt install nginx -y

- Clone my repository
    - git clone https://github.com/E335-comma/ALTSCHOOL-SECONDSEMESTER-EXAM


- Move the cloned repository to nginx web server default webpage directory
    - Command: sudo mv ALTSCHOOL-SECONDSEMESTER-EXAM/* /var/www/html/

- Install Certbot for SSL
    - Command: sudo apt install certbot python3-certbot-nginx -y

- Enable HTTPS on my domain name
    - Command: sudo certbot --nginx

---

## Step 5: Securing the Landing Page with HTTPS (Bonus Task)

Here are some reasons as to why it is important to secure a website with HTTPS:

- It protect sensitive information from attackers
- It verwifies the authenticity of a website
- It builds trust ensuring secure communication
- It prevents impersonation and supports user confidence

---

## Submissions

---

### Domain name: Adeife08.jumpingcrab.com

### Public IP Address: 16.171.28.67

### Public URL Address: https://adeife08.jumpingcrab.com/

### Screenshot:
Below are the images of my webpage with the ip address with no secured https and the image of the webpage with the custom domain with secured https.

---

## Challenges Faced

1. My nginx wasn't working after I installed it and tried to run it on my browser and I guessed it was due to unstable network, but it was later rectified.

2. My webpage wasn't showing that it is secured after my SSL certificate has been enabled, but I realised that it was because I didn't add HTTPS to my inbound in my instance security group, but after I added it the webpage showed that it is secure.  

![image alt](https://github.com/E335-comma/ALTSCHOOL-SECONDSEMESTER-EXAM/blob/main/Ip%20address.png)






