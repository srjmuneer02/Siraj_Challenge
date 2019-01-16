# Siraj_Challenge
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
```
aws cloudformation create-stack --stack-name myteststack01 --template-body file://Siraj_Challenge/cf-ec2.json --parameters ParameterKey=Vpc,ParameterValue=vpc-7aa04f1c  ParameterKey=EC2KeyName,ParameterValue=Ubuntu-12-Aug ParameterKey=Subnetid,ParameterValue=subnet-2f10bf74 ParameterKey=AssignedRole,ParameterValue=
```
Above command will create cloudfomation stack. you can see the progress in cloudformation management console
wait 5 mins
##Step 4: 

