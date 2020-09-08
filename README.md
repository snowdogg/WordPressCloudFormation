# WordPressCloudFormation
CloudFormation Template to launch a functional Wordpress server


Instructor Prompt:
I need you to crea
te the following:
- Cloudformation template to create the VPC (use the one that you did)

- Cloudformation template to create the RDS instance (mysql)

- Cloudformation template to create an EC2 and install and configure a wordpress server using the userdata

- Cloudformation template to create a route53 record for your wordpress public ip. (use the training.trambo.cloud hosted zone)

- A 'Main' cloudformation template from where you are calling the nested stacks

Notes:
You must configure the wordpress db connection from the cloudformation itself. dont do it manually

The idea is to launch the cloudformation stacks, then hit the DNS and start using wordpress

Deliverable
Push your cloudformation code in a personal github repository. Document everything on a README.md file and send the repo to me.
Document everything assuming that the person that is reading it doesnt have experience with cloudformation and either with AWS
