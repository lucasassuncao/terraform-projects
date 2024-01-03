# terraform-webserver-cluster

# Web Server Example

This folder contains an example [Terraform](https://www.terraform.io/) configuration that deploys a cluster of web servers (using [EC2](https://aws.amazon.com/ec2/) and [Auto Scaling](https://aws.amazon.com/autoscaling/)) and a load balancer (using [ELB](https://aws.amazon.com/elasticloadbalancing/)) AWS. The load balancer listens on port 80 and returns the text "Hello, World" for the `/` URL.

## Pre-requisites

* You must have installed on your computer. 
* You must have an AWS account.


## Quick start

**NOTE: This example will deploy real resources into your AWS account. Remember to destroy all resources after your tests to avoid any charges from AWS** 

### Configure your [AWS access keys](http://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys) as environment variables:

#### Linux
```bash
export AWS_ACCESS_KEY_ID=(your access key id)
export AWS_SECRET_ACCESS_KEY=(your secret access key)
```
#### PowerShell
```powershell
$env:AWS_ACCESS_KEY_ID="(your access key id)"
$env:AWS_SECRET_ACCESS_KEY="(your secret access key)"
```


#### Deploy the code:

```
terraform init
terraform apply
```

When the `apply` command completes, it will output the DNS name of the load balancer. To test the load balancer:

```
curl http://<alb_dns_name>/
```

#### Clean up when you're done:

```
terraform destroy
```
