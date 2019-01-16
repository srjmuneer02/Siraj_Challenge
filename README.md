# Siraj Challenge
## Summary
We will run the cloudfomarion template  named "cf-ec2.json". This template spin-up a EC2 instance and the instance ansible, then runs the ansible playbook for nginx https webserver setup

# Steps to Excute this cloudformation template with asible playbook is given below
## Step 1: Create an User in aws account for cli access
Login to aws management console, then navigate to IAM roles service.

Create one User with programming access and download Access key and secret key.

Then assigned administrator access to this user.

Open an command prompt in my PC and run the below command
```
aws configure
```
above command will ask for  Access key and secret key. Please provide that

## Step 2: CLone this git repo in your local repo with the following command 
```
git clone https://github.com/srjmuneer02/Siraj_Challenge.git
```
Above command will copy the files from github repo to local pc Siraj_Challenge folder

## Step 3: Create a cloudfomation stack from the template file with following command 

Goto EC2 managment console, then goto keypair section and create a key. This will be usefull for ssh if needed
goto VPC managment colsole, then get the default vpc-id and any one subnet-id  and fill these three values in the command below
```
aws cloudformation create-stack --stack-name myteststack01 --template-body file://Siraj_Challenge/cf-ec2.json --parameters ParameterKey=Vpc,ParameterValue=vpc-7aa04f1c ParameterKey=Subnetid,ParameterValue=subnet-2f10bf74  ParameterKey=EC2KeyName,ParameterValue=Ubuntu-12-Aug  ParameterKey=AssignedRole,ParameterValue=
```
Above command will create cloudfomation stack. you can see the progress in cloudformation management console

wait 5 mins

## Step 4: 

Check for new instance in EC2 managment console. Check the public ip for that instance and put that IP in your Browser.
http://<public-ip>
  
It will automatically redirect to https://<public-ip>. you might get some certificate authority waring as it has self signed certificate

## Debugging details

Total boostrap log for instance is located at /var/log/syslog

Ansible logs are located at /tmp/ansible.out.log

# Technical Details

cloudfomation stack creates EC2 instance and security group with port 80(http:userd for ssl redirect), 443(https) & 22(ssh:just).
EC2 instance runs bootsrap script at startup, this script installs ansible and run the ansible playbook

Ansible playbook install and configure nginx server with self signed certificate and hello world demo html page. it redirect from http protocol to https as well

# Python Coding

Solution for the credit card problem is aviable in filename credit_card_test.py in this repo

simple run that in python 3.5 and above. Enter the credit card number and program will say wether its valid or not
Below qare the details of regex used

Identifiers
--------------------

/d - any number

/b - check for whitespace

/s - space

/w - any character

. any character,  except for a newline

/. a period

--------------------
Modifiers
--------------------

{1,3} we are expecting 1-3

 \+ Match 1 or more

 \? Match 0 or 1

 \* Match 0 or more

 \$ Match the end of a string

 ^ matching the beggining of a string

 | either or 

 [] range of "variance"

 {x} expecting "x" amount


