
CloudFormation Template to launch a Wordpress server

Created By Andreas Cary

![wireframe of resources created](/wireframe.png "wireframe of resources created")

*notes:* user must have a route53 zone created and must replace HostedZoneId and Name properties of the route 53 record set in __route53.yml__ or this will not work as you will not have access to the zone I used. In addition please examine the TemplateURL property of the nested stacks found in __master.yml__ and replace them with your own s3 locations where you end up hosting your modified nested stacks. 


# master.yml
master.yml contains four nested stacks: vpc.yml, rds.yml, ec2wordpress.yml, and route53.yml

# vpc.yml
vpc.yml creates 2 public subnets connected to the outside world by an internet gateway, a nat gateway which lives in public subnet 1, and two private subnets, and appropriate routing tables

# rds.yml
rds.yml creates a mysql database in private subnet 1. We create this stack before the ec2 so that we are able to connect the ec2 instance to this database upon launch. The appropriate security group exposing port 3306 and accepting traffic from the public subnets is also created.

# ec2wordpress.yml
EC2wordpress creates an EC2 instance in public subnet 1 which connects to the RDS instance created in the previous stack. Security group allows HTTP and HTTPS traffic and incoming MySQL traffic. UserData script runs upon launch and configures database connection and installs wordpress.

# route53.yml
Route53 ties the instance to a domain name so it can easily be accessed in the browser. Remember to modify for your personal use as mentioned above.
