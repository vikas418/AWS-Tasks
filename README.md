# Assignment 01 📘

## 📝 Problem Statements

### In this assignment, you will learn about various deployment strategies:

- 🔄 **Recreate Deployment**
- 🔄 **Rolling Deployment**
- 🔵🟢 **Blue-Green Deployment**
- 🅰️🅱️ **A/B Deployment**
- 🐤 **Canary Deployment**

### You need to implement these two deployment strategies:

## Must Do

- 🔄 **Recreate Deployment**
- 🔄 **Rolling Deployment**

### Good to Do

- 🔵🟢 **Blue-Green Deployment**
- 🐤 **Canary Deployment**

## Recommendation

- 🚀 **Don't jump straight into creating the utility.** Perform manual steps first.

### GitHub-Link 🔗

~~~
https://github.com/OT-TRAINING/DeploymentStrategies
~~~

## Hint🔍 : 
1. Use ASG
2. Use LB
3. Use EC2 service
4. Use AMI Snapshot

# 🛠 ImpleMentation :-

# 🔄 Recreate Deployment:
## Basic Requirements :

### - ☁️ **Create VPC**

![VPC](https://github.com/vikas418/AWS-Tasks/assets/149520276/a4469ccd-6265-45a3-9fb4-c2dc4d73473b)

### - 🌐 **Create 2 Public Subnets**

![Two Public Subnet](https://github.com/vikas418/AWS-Tasks/assets/149520276/0739d806-5bbb-4055-83ae-197e5aa22132)

### - 🔒 **Create 2 Private Subnets**

![Two Private Subnet](https://github.com/vikas418/AWS-Tasks/assets/149520276/f1390202-62e6-432c-a0e2-dfb664caaeca)

### - 🛣️ **Create Route Table (Public & Private)**

![Route Tables (Pub   Private)](https://github.com/vikas418/AWS-Tasks/assets/149520276/13bb98ec-becf-4e51-9e3e-785be251a0b0)

### - 🌐 **Create IGW Gateway**

![Internet Gateway](https://github.com/vikas418/AWS-Tasks/assets/149520276/ca819980-cff7-49fa-8a83-46ada2bbad73)

### - 🌐 **Create NAT Gateway**

![NAT Gateway](https://github.com/vikas418/AWS-Tasks/assets/149520276/a397e973-220f-457d-b578-2a73241f4f21)

### - 🖥️ **Create instances for Private1 & Private2**

![Two Private Servers](https://github.com/vikas418/AWS-Tasks/assets/149520276/fb5f3452-bee0-48f1-a808-f5bd20066293)

### - 🖼️ **Make the AMI of it**

![AMI(Both)](https://github.com/vikas418/AWS-Tasks/assets/149520276/68930ab3-af1c-4ca5-bcdc-a5bc2159e68d)

### - 🎯 **Create a Target group for Load Balancer**

![Target Group with 2 Server setup with Nginx](https://github.com/vikas418/AWS-Tasks/assets/149520276/82d58aee-99d1-4b89-a9ab-d41c9dff7a26)

### ⚖️ **Create a Load Balancer and attach Target Group to it**

![Load Balancer With Port 80](https://github.com/vikas418/AWS-Tasks/assets/149520276/2cef852b-17e3-4170-8532-1002a6d997a1)

### - 🚀 **Create a Launch Template, Create an Autoscaling group and attach Load Balancer to it**
 
![Launch Template](https://github.com/vikas418/AWS-Tasks/assets/149520276/abd6c246-4d4f-48a1-be2d-a1f700c16a9d)

### - 🌐 **Go to web browser and hit the Load Balancer DNS**

![V1 SS](https://github.com/vikas418/AWS-Tasks/assets/149520276/e0e8e473-f1dd-44a5-b5a6-9bdb03582603)

### - 🚀 **Now change the version in Launch template and Go to the auto scaling group and change the capacity to zero**

### - 🖼️ **It will show downtime and then increase the capacity. When the instance gets up it will show V2**

![Launch Template for V2 ](https://github.com/vikas418/AWS-Tasks/assets/149520276/b4cbb2dc-fd90-44b5-a934-27dbee785624)

- 🚫 **It will show Temporarily Unavailable**

![Error SS](https://github.com/vikas418/AWS-Tasks/assets/149520276/cdf8370f-9232-4aa4-acf0-c118974a04c8)

### - :white_check_mark: After Increasing the Desired State to Count 2 It will Show the Website Up & Running With Version2(V2)

![V2 SS](https://github.com/vikas418/AWS-Tasks/assets/149520276/ae99e801-4983-4a67-aea8-8af23d7a9b2c)


# 2. Rolling Deployment :-

- :white_check_mark: **Here we use the same infrastructure as above:**

- 📈 **I have 3 servers running in appv1 as shown below. By changing the capacity in Autoscaling group**

![Three Servers For Rolling Deployment](https://github.com/vikas418/AWS-Tasks/assets/149520276/8c070fae-6b9e-4687-8b39-b8e7ab64320b)

![Register Target for appv1 and appv2 Rolling Deployment](https://github.com/vikas418/AWS-Tasks/assets/149520276/8005ae00-2508-49ba-97d4-06eae187d732)

- 📉 **It will gradually increase the instances then we change the capacity in autoscaling group to desired as shown in below screenshots**

![Changing Capacity in Auto-Scaling-Group It will Decrease the No  of Instances ](https://github.com/vikas418/AWS-Tasks/assets/149520276/39050dc4-29c2-43fe-b9df-8adb183fffe2)

![Private Server With Two appv1 and appv2](https://github.com/vikas418/AWS-Tasks/assets/149520276/b46da2df-33c7-4ec8-8810-2ab2b41e7d2e)

- 📈 **So due to this v1 replaces the v2 gradually with no downtime**

- :white_check_mark: **Version-1**

![V1 SS](https://github.com/vikas418/AWS-Tasks/assets/149520276/9ccaadfe-cafe-41ee-aa64-53dc57987935)

- :white_check_mark: **Version-2** 

![V2 SS](https://github.com/vikas418/AWS-Tasks/assets/149520276/e7dfde5b-f078-4f97-a511-f49059048838)






## ✍️ Author :copyright:

- [Vikas Bandi](https://github.com/vikas418)
