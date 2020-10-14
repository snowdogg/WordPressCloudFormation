# WordPress Stack w/ CloudFormation

Cloudformation template using nested stacks to launch an empty (new) WordPress site and host it on Route 53. Resources created include a VPC, MySQL RDS Database Instance, EC2 Instance, and a Route 53 Domain.

![wireframe of resources created](/wireframe.png "wireframe of resources created")

## Prerequisites

You must have an AWS Account to use CloudFormation. You must also upload the yml files contained in this repository to an S3 bucket and make the contents accessible to the public. You must also create a hosted zone.

## Important Changes

After uploading the yml files to an S3 bucket, please make sure to change the TemplateURL parameter on all of the nested stacks to reflect your S3 bucket's unique path.

#### Master.yml
```yaml
TemplateURL: your s3 url goes here
```

#### route53.yml
```yaml
HostedZoneId: yourhostedzoneidgoeshere
Name: your.hosted.zone.here
```

## License
[MIT](https://choosealicense.com/licenses/mit/)