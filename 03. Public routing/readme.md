# PUBLIC ROUTUNG SETUP

## DEFINITIONS
----

### Subnet

### Internet Gateway

**Internet Gateway** is a VPC component that allows communication between instances in your VPC and the internet

### Route Table

A **Route table** contains a set of rules, called routes, that are used to determine where network traffic is directed.

### Route

Specifies a route in a **Route table** within a VPC.

## STEPS
---

1. ENABLE AUTO ASSIGN IP ADDRESS FOR SUBNET: **publicOne**. 

    This feature allows to automatically request a public IPv4 address for instances launched into this subnet.
    
    * Go to **VPC** section in the AWS console
    * Click **Subnets** in the left-hand menu.
    * Select **publicOne** subnet, then click **Action** and **Modify auto-assign IP settings**
    * Click **Save** 

2. ENABLE AUTO ASSIGN IP ADDRESS FOR SUBNET: **publicTwo**.

    This feature allows to automatically request a public IPv4 address for instances launched into this subnet.
    
    * Go to **VPC** section in the AWS console
    * Click **Subnets** in the left-hand menu.
    * Select **publicTwo** subnet, then click **Action** and **Modify auto-assign IP settings**
    * Click **Save** 

3. CREATE AN INTERNET GATEWAY

    * Go to **VPC** section in the AWS console
    * Click **Internet Gateways** in the left-hand menu.
    * Name your internet gateway as **igw** by completing the **Name tag** form field
    * Click **Create**
    * Select the Internet Gateway created in the previous step and click **Actions** then **Attach to VPC**
    * Select the VPC created in the previous step of this lab, then click **Attach**

4. CONFIGURE ROUTING
    
    * Go to **VPC** section in the AWS console
    * Click **Route Tables** in the left-hand menu
    * Click **Create route table**
    * Name your route table as **public** by completing the **Name tag** form field
    * Select the VPC created in the previous step of this lab, then click **Create**
    * Click **Close**
    * On the list find previously created **Route Table** and select it
    * Go to the **Routes** tab at the bottom of the screen
    * Click **Edit routes**
    * Click **Add route**
    * As a destination put **0.0.0.0/0** and as a target Internet Gateway created earlier by you. 
    * Click **Save routes** then **Close**

5. ASSOCIATE SUBNETS WITH ROUTE TABLE

    * Make sure that your public route table is still selected
    * Go to the **Subnet Associations** tab at the bottom of the screen
    * Click **Edit subnet associations** 
    * Find the subnet **publicOne** and **publicTwo**, select them and click **Save**

## END OF LAB

Now you should have a connectivity form the public subnets to the internet and you can go to the next section of this lab 
