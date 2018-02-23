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
