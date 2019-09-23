# PRIVATE INTERNET CONNECTIVITY

## DEFINITIONS
----

### Subnet

### Nat Gateway

Enable instances in a private subnet to connect to the internet or other AWS services, but prevent the internet from initiating a connection with those instances.

### Elastic IP

IP address associated with your AWS account which could be easily assigned to any instance in your account.

### Route Table

A **Route table** contains a set of rules, called routes, that are used to determine where network traffic is directed.

### Route

Specifies a route in a **Route table** within a VPC.

## STEPS
---

1. CREATE NAT GATEWAY IN "PUBLIC ONE" SUBNET 

    * Go to **VPC** section in the AWS console
    * Click **NAT Gateways** in the left-hand menu.
    * Click **Create NAT Gateway**
    * Select **publicOne** subnet
    * Click **Create New EIP**
    * Click **Create a NAT Gateway** button
    * Click **Close**
    * Note ID of created NAT 

2. CREATE NAT GATEWAY IN "PUBLIC TWO" SUBNET 
    
    * Go to **VPC** section in the AWS console
    * Click **NAT Gateways** in the left-hand menu.
    * Click **Create NAT Gateway**
    * Select **publicTwo** subnet
    * Click **Create New EIP**
    * Click **Create a NAT Gateway** button
    * Click **Close**
    * Note ID of created NAT

3. CONFIGURE ROUTING FOR "PRIVATE ONE" SUBNET

    * Go to **VPC** section in the AWS console
    * Click **Route Tables** in the left-hand menu
    * Click **Create route table**
    * Name your route table as **privateOne** by completing the **Name tag** form field
    * Select the VPC created in the previous step of this lab, then click **Create**
    * Click **Close**
    * On the list find previously created **Route Table** and select it
    * Go to the **Routes** tab at the bottom of the screen
    * Click **Edit routes**
    * Click **Add route**
    * As a destination put **0.0.0.0/0** and as a target NAT GATEWAY ( you noted ID in step one )created earlier by you. 
    * Click **Save routes** then **Close**

4. CONFIGURE ROUTING FOR "PRIVATE TWO" SUBNET

    * Go to **VPC** section in the AWS console
    * Click **Route Tables** in the left-hand menu
    * Click **Create route table**
    * Name your route table as **privateOne** by completing the **Name tag** form field
    * Select the VPC created in the previous step of this lab, then click **Create**
    * Click **Close**
    * On the list find previously created **Route Table** and select it
    * Go to the **Routes** tab at the bottom of the screen
    * Click **Edit routes**
    * Click **Add route**
    * As a destination put **0.0.0.0/0** and as a target NAT GATEWAY ( you noted ID in the step two created earlier by you. 
    * Click **Save routes** then **Close**

5. ASSOCIATE "SUBNET ONE" WITH "ROUTE TABLE ONE"

    * Make sure that your **privateOne** route table is selected
    * Go to the **Subnet Associations** tab at the bottom of the screen
    * Click **Edit subnet associations** 
    * Find the subnet **privateOne** select them and click **Save**

6. ASSOCIATE "SUBNET TWO" WITH "ROUTE TABLE TWO"

    * Make sure that your **privateTwo** route table is selected
    * Go to the **Subnet Associations** tab at the bottom of the screen
    * Click **Edit subnet associations** 
    * Find the subnet **privateTWo** select them and click **Save**

## END OF LAB

Now all your resources in private subnets should be able to initialize internet connections, but those resources won't be accessible from the internet
