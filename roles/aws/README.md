# MultiCloud VM Deployment [ AWS ]
<p >
  <a href="https://aws.amazon.com/"><img src="files/aws.png" width="150" height="70" title="Amazon Web Services"></a>
  </p>



This Component provides automated deployment of of virtual machine (EC2 Instance) on AWS. 

## Product Information
--------------------
Product: AWS

Vendor: Amazon

Vendor Site: https://aws.amazon.com/

Version Supported: N/A

## Requirements
------------

Tested Operating Systems

- UBUNTU 18.04 LTS / UBUNTU 20.04 LTS

Operating System Pre-Requisites

- Linux Machine
	  
## Dependencies
------------
1. [boto3](https://boto3.amazonaws.com/v1/documentation/api/latest/guide/quickstart.html) `Python SDK for AWS`


## Installation and Configuration

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install boto3.

```
pip3 install boto3
```





## Modules
------------------


1- `ec2`: This only one module used to perform all actions on EC2 instance


## Role Variables


| Variable Name   | Variable Description   |  Example Value of Variable | Variable Type
| :---------------| :----------------------| :--------------------------| :----------------
|  {{ image }} | AMI ID to use for the instance.(OS Flavour)  | ami-040c7ad0a93be494e | user-input
|  {{ security_group }}  | Security groups can provide an efficient way to assign access to resources on your network | Security_Group01 | user-input
|  {{ instance_type }}  | Instance type defines size of resouces to be used with instance (CPU,Disk,Memory)  | t2.micro |  user-input
| {{ count }} | specifies number of instance to be spawned | 2 | user-input
|  {{ keypair }}  |  Keypair is used to access your instance via SSH or Putty  |  keypai01 | Default
| {{ region }} | reagion/zone in which your instance is located | south-ap-1 | Default



## Extra variables JSON structure
```
{
    "extra_vars": {
        "provider_type": "aws",
        "resource_config": {
            "security_group": "SOL-SecurityGroup",
            "instance_type": "t2.micro",
            "image": "ami-0e306788ff2473ccb",
            "keypair": "nikhil-aws",
            "region": "ap-south-1",
            "vm_name": "nikhil-sol-0001"
        },
        "tower_config": {
            "tower_hostname": "http://192.168.43.191",
            "tower_username": "admin",
            "tower_password": "cGFzc3dvcmQ=",
            "inventory_name": "SOL-AWS"
        },
        "group_name": "Linux"
    }
}
```


License
-------
© Copyright 2020  `Great Software Laboratory`. All rights reserved.
