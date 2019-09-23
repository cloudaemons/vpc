# Network ACLs

## DEFINITIONS
----

### Network ACLs

Network ACLs. A network access control list (ACL) is an optional layer of security for your VPC that acts as a firewall for controlling traffic in and out of one or more subnets. You might set up network ACLs with rules similar to your security groups in order to add an additional layer of security to your VPC.

## STEPS
---

1. CHANGE NETWORK ACLS

    * Go to **VPC** section in the AWS console
    * Click **Network ACLs** in the left-hand menu.
    * Find default network ACL assigned to your VPC
    * Click **Edit inbound rules**
    * Change Rule where you have **All traffic** on source **0.0.0.0/0** to **DENY**
    * Click **Save**
    * Go to EC2 instances, find IP of your public instance,  then try to open it in a web browser
    * The access should be forbidden

## END OF LAB




