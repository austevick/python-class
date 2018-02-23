## Boto
+++
[Boto](http://boto3.readthedocs.io/en/latest/) is the Python SDK for AWS. There are two major versions of boto out int he wild, boto2 and boto3. Boto2 has been deprecated for years so be sure to use boto3 instead.
+++
Boto3 is split between 2 packages, [boto3](https://github.com/boto/boto3) and [botocore](https://github.com/boto/botocore). Botocore is the low-level, core functionality of boto3. Botocore mostly deals with authentication (signing the request) and making the request.
+++
Boto3 mostly deals with higher level functionality such as converting the response to json or a native python type.
+++
### Installation & Setup
Installing boto3 is easy, you just install through pip
```
pip install boto3
```
Configuration (setting up access key) is just as easy. The easiest way is to use the aws cli
```
aws configure
```
+++
If you don't have the aws cli, you can just create a file at `~/.aws/credentials` with
```
[default]
aws_access_key_id = YOUR_ACCESS_KEY
aws_secret_access_key = YOUR_SECRET_KEY
```
and create ~/.aws/config with
```
[default]
region=us-east-1
```
+++
When running boto3 on an EC2 instance or a ECS Task, boto3 will automatically try and fetch credentials from the IAM instance profile/ECS Task Role.
+++
There are two ways to work with boto3. The easiest is using the `Resource` class. The resource class exposes specific services as a class where the properties are properties of the AWS "thing" and the methods are API actions (i.e. StopInstances).
```
import boto3
ec2 = boto3.resource('ec2')
```
+++
The `Resource` class also exposes collections which make fetching AWS resources super easy:
```
import boto3
ec2 = boto3.resource('ec2')
for instance in ec2.instances.all():
    print instance.instance_id
```
+++
We can also filter for resources based on the filters available for that resource.
+++
```
import boto3
ec2 = boto3.resource('ec2')
for instance in ec2.instances.filter(Filters=[{
    'Name':'tag:Name',
    'Values':['Test']
}]):
    print instance.instance_id
```
@[4-5](The filters are a list of key/value pairs)
@[4](There will always be a Name key when using filters)
@[4](In this scenario I am filtering based on the tags of the instance. I am using the tag Name)
@[4](For using a tag name, you need to specify the value in the format tag:tag_name)
@[4](So in my case I us tag:Name since the key of my tag is Name)
@[5](There will also always be another key called Values which takes a list of strings)
@[5](In my case, I only have one value I'm interested in)
+++
You can also create ec2 instances using the resource class
+++
```
import boto3
ec2 = boto3.resource('ec2')
config = {
    "ImageId":"ami-97785bed",
    "MaxCount":1,
    "MinCount":1,
    "KeyName":"austin",
    "InstanceType":"t2.medium",
    "SecurityGroups":['SSH','default','HTTP'],
    "TagSpecifications:[{
        "ResourceType":"instance",
        "Tags":[{
            "Key':"Name",
            "Value":"Launched from Boto"
        }]
    }],
    "UserData":"""#!/bin/bash
        yum update -y
        yum install -y httpd24 php56 mysql55-server php56-mysqlnd
        service httpd start
        chkconfig httpd on
        groupadd www
        usermod -a -G www ec2-user
        chown -R root:www /var/www
        chmod 2775 /var/www
        find /var/www -type d -exec chmod 2775 {} +
        find /var/www -type f -exec chmod 0664 {} +
        echo "<?php phpinfo(); ?>" > /var/www/html/phpinfo.php"""
}
instance = ec2.create_instances(**config)
```
@[3-29](We hold the parameters we want our instance to have in a dict)
@[30](The **config syntax means to "unpack" the dictionary. What this is doing is turning each key/value pair into a argument for the create_instances method)
