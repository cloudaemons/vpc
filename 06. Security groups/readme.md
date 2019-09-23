# SECURITY GROUPS

## DEFINITIONS
----

### Subnet

### Security groups

AWS security groups are associated with instances and provide security at the protocol and port access level. Each security group – working much the same way as a firewall – contains a set of rules that filter traffic coming into and out of an EC2 instance. There are no ‘Deny’ rules. Rather, if no rule explicitly permits a particular data packet, it will be dropped.

## STEPS
---

1. CREATE SECURITY GROUP WHICH ALLOW SSH

    * Go to **EC2** section in the AWS console
    * Click **Security Groups** in the left-hand menu
    * Click **Create Securoty Group**
    * Name your security group **mySgSsh**
    * Add description
    * Select VPC which you created ealier
    * Make sure that **Inbound** tab is selected
    * Click **Add rule** then select type  **SSH** 
    * As a source set **0.0.0.0/0** (Warning: having 0.0.0.0/0 is bad practise, use only for training purposes )
    * Click **Create**


2. CREATE SECURITY GROUP WHICH ALLOW SENDING WEB TRAFIC
    
    * Go to **EC2** section in the AWS console
    * Click **Security Groups** in the left-hand menu
    * Click **Create Securoty Group**
    * Name your security group **mySgWeb**
    * Add description
    * Select VPC which you created ealier
    * Make sure that **Inbound** tab is selected
    * Click **Add rule** then select type  **HTTP** 
    * As a source set **0.0.0.0/0**
    * Click **Add rule** then select type  **HTTPS** 
    * As a source set **0.0.0.0/0**

3. CREATE SECURITY GROUP WHICH ALLOW ICMP (PING)

    * Go to **EC2** section in the AWS console
    * Click **Security Groups** in the left-hand menu
    * Click **Create Securoty Group**
    * Name your security group **myIcmpb**
    * Add description
    * Select VPC which you created ealier
    * Make sure that **Inbound** tab is selected
    * Click **Add rule** then select type  **All ICMP - IPV4** 
    * As a source set **0.0.0.0/0**

## END OF LAB

You have created security groups which will be used in the next sections of this lab
