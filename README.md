# AWS-Tasks
## Load Balancer Task With Rolling and Recreate Deployment


# Assignment 01

## 📝 Problem Statements

### In this assignment, you will learn about various deployment strategies:

- 🔄 **Recreate Deployment**
- 🔄 **Rolling Deployment**
- 🔵🟢 **Blue-Green Deployment**
- 🅰️ **A/B Deployment**
- 🐤 **Canary Deployment**

### You need to implement these two deployment strategies:

## Must Do

- 🔄 **Recreate Deployment**
- 🔄 **Rolling Deployment**

### Good to Do

- 🟦 **Blue-Green Deployment**
- 🐤 **Canary Deployment**

## Recommendation

- 🚀 **Don't jump straight into creating the utility.** Perform manual steps first.

### GitHub Link
[Deployment Strategies Repository](https://github.com/OT-TRAINING/DeploymentStrategies)

## Hint:
1. Use **Auto Scaling Groups (ASG)**
2. Use **Load Balancers (LB)**
3. Use **EC2 Service**
4. Use **AMI Snapshots**

---

## Implementation:

### 🔄 1. Recreate Deployment

#### Basic Requirements:

1. **Create VPC**
   ![VPC](https://github.com/vikas418/AWS-Tasks/assets/149520276/a4469ccd-6265-45a3-9fb4-c2dc4d73473b)
   
2. **Create 2 Public Subnets**
   ![Two Public Subnets](https://github.com/vikas418/AWS-Tasks/assets/149520276/0739d806-5bbb-4055-83ae-197e5aa22132)
   
3. **Create 2 Private Subnets**
   ![Two Private Subnets](https://github.com/vikas418/AWS-Tasks/assets/149520276/f1390202-62e6-432c-a0e2-dfb664caaeca)
   
4. **Create Route Table (Public & Private)**
   ![Route Tables (Public & Private)](https://github.com/vikas418/AWS-Tasks/assets/149520276/13bb98ec-becf-4e51-9e3e-785be251a0b0)
   
5. **Create Internet Gateway (IGW)**
   ![Internet Gateway](https://github.com/vikas418/AWS-Tasks/assets/149520276/ca819980-cff7-49fa-8a83-46ada2bbad73)
   
6. **Create NAT Gateway**
   ![NAT Gateway](https://github.com/vikas418/AWS-Tasks/assets/149520276/a397e973-220f-457d-b578-2a73241f4f21)
   
7. **Create Instances for Private1 & Private2**
   ![Two Private Servers](https://github.com/vikas418/AWS-Tasks/assets/149520276/fb5f3452-bee0-48f1-a808-f5bd20066293)
   
8. **Make the AMI of the Instances**
   ![AMI](https://github.com/vikas418/AWS-Tasks/assets/149520276/68930ab3-af1c-4ca5-bcdc-a5bc2159e68d)
   
9. **Create a Target Group for Load Balancer**
   ![Target Group with 2 Servers Setup with Nginx](https://github.com/vikas418/AWS-Tasks/assets/149520276/82d58aee-99d1-4b89-a9ab-d41c9dff7a26)
   
10. **Create a Load Balancer and Attach Target Group**
    ![Load Balancer with Port 80](https://github.com/vikas418/AWS-Tasks/assets/149520276/2cef852b-17e3-4170-8532-1002a6d997a1)
    
11. **Create a Launch Template, Create an Auto Scaling Group, and Attach Load Balancer**
    ![Launch Template](https://github.com/vikas418/AWS-Tasks/assets/149520276/abd6c246-4d4f-48a1-be2d-a1f700c16a9d)
    
12. **Go to Web Browser and Hit the Load Balancer DNS**
    ![V1 Screenshot](https://github.com/vikas418/AWS-Tasks/assets/149520276/e0e8e473-f1dd-44a5-b5a6-9bdb03582603)
    
13. **Change the Version in Launch Template, Set Auto Scaling Group Capacity to Zero, and then Increase Capacity**
    - Shows Downtime
    ![Launch Template for V2](https://github.com/vikas418/AWS-Tasks/assets/149520276/b4cbb2dc-fd90-44b5-a934-27dbee785624)
    - Temporarily Unavailable
    ![Error Screenshot](https://github.com/vikas418/AWS-Tasks/assets/149520276/cdf8370f-9232-4aa4-acf0-c118974a04c8)
    - Increase Desired State to 2, Showing Version2 (V2)
    ![V2 Screenshot](https://github.com/vikas418/AWS-Tasks/assets/149520276/ae99e801-4983-4a67-aea8-8af23d7a9b2c)

---

### 🔄 2. Rolling Deployment

1. **Reuse Same Infrastructure as Above**
2. **Running 3 Servers in AppV1 by Changing Capacity in Auto Scaling Group**
    ![Three Servers for Rolling Deployment](https://github.com/vikas418/AWS-Tasks/assets/149520276/8c070fae-6b9e-4687-8b39-b8e7ab64320b)
    ![Register Target for AppV1 and AppV2](https://github.com/vikas418/AWS-Tasks/assets/149520276/8005ae00-2508-49ba-97d4-06eae187d732)
3. **Increase Instances Gradually, Change Capacity in Auto Scaling Group to Desired State**
    ![Changing Capacity in Auto Scaling Group](https://github.com/vikas418/AWS-Tasks/assets/149520276/39050dc4-29c2-43fe-b9df-8adb183fffe2)
    ![Private Server with AppV1 and AppV2](https://github.com/vikas418/AWS-Tasks/assets/149520276/b46da2df-33c7-4ec8-8810-2ab2b41e7d2e)
4. **Gradual Replacement of V1 by V2 with No Downtime**
    - Version-1
    ![V1 Screenshot](https://github.com/vikas418/AWS-Tasks/assets/149520276/9ccaadfe-cafe-41ee-aa64-53dc57987935)
    - Version-2
    ![V2 Screenshot](https://github.com/vikas418/AWS-Tasks/assets/149520276/e7dfde5b-f078-4f97-a511-f49059048838)

---

## ✍️ Authors

- [Vikas Bandi](https://github.com/vikas418)
