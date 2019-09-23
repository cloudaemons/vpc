# EC2 Instances

## DEFINITIONS
----

### EC2 Instance

An EC2 instance is a virtual server in Amazon's Elastic Compute Cloud (EC2) service which allows running different applications 

### Bastion Host

Bastion host in your VPC environment enables you to securely connect to your Linux instances without exposing your environment to the Internet. After you set up your bastion hosts, you can access the other instances in your VPC through Secure Shell (SSH) connections on Linux. Bastion hosts are also configured with security groups to provide fine-grained ingress control.

## STEPS
---

1. CREATE KEY PAIRS WHICH ALLOW TO ACCESS EC2 VIA SSH

    * Go to **EC2** section in the AWS console
    * Click **Key Pairs** in the left-hand menu
    * Click **Create Key Pair**
    * Name the key **myKey**
    * Click **Create**. It should generate **myKey.pem**. Save this file on your local computer
     
2. LAUNCH EC2 INCATNCE IN THE PUBLIC SUBNET

    * Go to **EC2** section in the AWS console
    * Click **Launch Instance**
    * Choose **Amazon Linux 2 AMI (HVM), SSD Volume Type** then click **Select**
    * Select **t2.micro** as an instance type
    * Click **Next: Configure Instance Details**
    * Select previously created VPC, in the field **Network**
    * Select **publicOne** in the field **Subnet**
    * In section **Advenced Datails**, add code listed below in the field **User data**
    
    ```bash
    #!/bin/bash
    sudo yum install -y httpd
    sudo service httpd start
    ```
    
    * Click **Next: Add Storage** button
    * You can modify here the size of disk attached to your instance
    * Click **Next: Add Tags**
    * Go to security group section by clicking **Next: Configure Security Group**
    * Select an existing security group
    * Choose **mySgWeb** and **mySgSsh** security group
    * Click **Review and launch**
    * Click **Launch**
    * Choose an existing key pair previously created
    * Acknowledge that you have access to the selected private key file
    * Click **Launch Instance** then **View instances**
    * Select created instance and find the **IPv4 Public IP**, copy it and open in the browser, a web server should be running
    * Go to **EC2** section in the AWS console
    * Click **Instances** in the left-hand menu
    * Select your newly created instance
    * Click **connect**
    * Select **EC2 Instance Connect (browser-based SSH connection)**
    * * Click **Connect**  it should connect you to your public virtual machine


3. LAUNCH EC2 INCATNCE IN THE PRIVATE SUBNET

    * Go to **EC2** section in the AWS console
    * Click **Launch Insstance**
    * Choose **Amazon Linux 2 AMI (HVM), SSD Volume Type** then click **Select**
    * Select **t2.micro** as an instance type
    * Click **Configure Instance Details**
    * Select previously created VPC, in the field **Network**
    * Select **privateOne** in the field **Subnet**
    * Click **Next: Add Stroage** button
    * You can modify here size of disk attached to your instance
    * Click **Next: Add Tags**
    * Go to security group section by clicking **Next: Configure Securoty Group**
    * Select an existing security group
    * Choose **mySgSsh** and **myIcmpb** security groups
    * Click **Review and launch**
    * Click **Launch**
    * Choose an existing key pair previously created
    * Acknowledge that you have access to the selected private key file
    * Click **Launch Instance** then **View instances**
    * Your Instance should be created

4. USE BASTION HOST TO CONNECT YOUR PRIVATE EC2 INSTANCE

    Your private instance is only available from VPC, so to connect to private instance you have to firstly log in to instance in public subnet, then from this instance login to a private instance
    
    * Go to **EC2** section in the AWS console
    * Click **Instances** in the left-hand menu
    * Select your private EC2 Instance
    * Find the private IP and note it
    * Select your public EC2 Instance
    * Click **connect**
    * Select **EC2 Instance Connect (browser-based SSH connection)**
    * Click **Connect**  it should connect you to your public virtual machine
    * Ping the private instance, you should receive a response from your private EC2
    
    ```bash
    ping ipOfPrivateInstance
    ```

## END OF LAB

You have created ec2 instances, now you can go to the next part of this lab
