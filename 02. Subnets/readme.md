# SUBNETS SETUP

## DEFINITIONS
----

### Subnet

A part of VPC with specified IP addresses.

### Public Subnet

A subnet with access to the internet

### Private Subnet

A subnet without access to the internet

## STEPS
---

1. CREATE PUBLIC SUBNET ONE

* Go to **VPC** section in the AWS console
* Click **Subnets** in the left-hand menu.
* Click **Create subnet**
* Name your subnet as **publicOne** by completing the **Name tag** form field
* Choose the VPC previously created
* Set the availability zone where this subnet will reside to **eu-west-1a**
* Set IPv4 CIDR block to 10.0.0.0/24
* Click **Create** and close out of the success message

2. CREATE PUBLIC SUBNET TWO

* Go to **VPC** section in the AWS console
* Click **Subnets** in the left-hand menu.
* Click **Create subnet**
* Name your subnet as **publicTwo** by completing the **Name tag** form field
* Choose the VPC previously created
* Set  the availability zone where this subnet will reside to **eu-west-1b**
* Set IPv4 CIDR block to 10.0.1.0/24
* Click **Create** and close out of the success message

3. CREATE PRIVATE SUBNET ONE

* Go to **VPC** section in the AWS console
* Click **Subnets** in the left-hand menu.
* Click **Create subnet**
* Name your subnet as **privateOne** by completing the **Name tag** form field
* Choose the VPC previously created
* Set the availability zone where this subnet will reside to **eu-west-1a**
* Set IPv4 CIDR block to 10.0.3.0/24
* Click **Create** and close out of the success message

4. CREATE PRIVATE SUBNET TWO

* Go to **VPC** section in the AWS console
* Click **Subnets** in the left-hand menu.
* Click **Create subnet**
* Name your subnet as **privateTwo** by completing the **Name tag** form field
* Choose the VPC previously created
* Set the availability zone where this subnet will reside to **eu-west-1b**
* Set IPv4 CIDR block to 10.0.4.0/24
* Click **Create** and close out of the success message


## END OF LAB

Your subnets are ready to use in the next section of this lab 
