
CloudFormation Template to launch a functional Wordpress server

Created By Andreas Cary

master contains a series of parameters and nested stacks

VPC creates two public subnets connected to the outside world with an internet gateway, a nat gateway which lives in public subnet 1, and two private subnets, with appropriate routing tables

RDS creates a mysql database in private subnet 1

EC2wordpress creates an EC2 instance in public subnet 1 which connects to the RDS instance created in the previous stack.

Route53 ties the instance to a domain name so it can easily be accessed in the browser.

Please remember to change the "TemplateURL" property of the nested stacks if you are editing and using your own nested stacks. Also would be a good idea to use a route 53 zone that you have permissions to use as that is also currently hard coded and would need to be changed if you want to use this stack :)