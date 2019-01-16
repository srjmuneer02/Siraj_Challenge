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

