# Custom plugins
In addition to built-in plugins, Amazon Q can be integrated with various third-party applications. Users can leverage natural language to query information and perform actions seamlessly.

## Setting up a System & Plugin
1. Download [the CloudFormation template](../oas-restaurant-booking.yaml) onto your local machine.  
2. Open the AWS Management Console and navigate to [AWS CloudFormation](https://console.aws.amazon.com/cloudformation).  
3. Select **Create stack** with **New resources (standard)**, then **Choose an existing template**, **Upload a template file**, click on **Choose file** and then upload the Cloudformation template you downloaded, and click **Next**.  
![custom-1](./img/custom-1.png)  
4. Input a stack name `custom-plugin-restaurant-stack`, Then select **Next**.  
![custom-2](./img/custom-2.png)  
5. Scroll down to the bottom, and check "I acknowledge that AWS CloudFormation might create IAM resources.". Then select **Next**.  
6. Scroll down to the bottom of the page and click *Submit*. Wait around 5 minutes until the CloudFormation stack status to be *CREATE_COMPLETE*.  
![custom-3](./img/custom-3.png)  

## Custom plugin setup
1. 

## Conversing with a System
