# Knowledge Base setup
In this lab, you will learn how to configure data sources using web crawlers, Upload files and Amazon S3 connectors to create knowledge bases and interact with an Amazon Q Business application to retrieve tailored information based on specific questions.  

## Web crawler data source
1. On the application details page, click **Data sources**.  
![kb-1](./img/kb-1.png)  

2. Click **Select retriever**. Under Retrievers select *Native (Recommended)*. For Index provisioning, choose Enterprise with Number of units set to 1 and then click **Confirm**.  
![kb-2](./img/kb-2.png)  

3. After successfully, click **Add data source**.  
![kb-3](./img/kb-3.png)  

4. First, we are going to configure a Web crawler data source.  
Select **Web Crawler**. Provide a Data source name `webcrawler`.  
Select **Source URLs** and provide Source URLs `https://docs.aws.amazon.com/prescriptive-guidance/latest/retrieval-augmented-generation-options/choosing-option.html`  
![kb-4](./img/kb-4.png)  

In **Authentication** and **Web proxy - optional** sections, leave settings as default.  
![kb-5](./img/kb-5.png)  

5. For **IAM role**, select the IAM role containing `-DataSourceRole-`.  
In **Sync scope** section, select Sync range to *Sync domains with subdomains only*, set Crawl depth to `0` and Maximum links per page to `5`.  
![kb-6](./img/kb-6.png)  

6. For **Sync mode**, set *Full synce*.  
For **Sync run schedule**, select *Run on demand* from the dropdown menu and click **Add data source**.  
![kb-7](./img/kb-7.png)  

7. After the data source is created, click **Sync now** to start the sync.  
![kb-8](./img/kb-8.png)  
It will take around 10-20 minutes to finish.  
![kb-9](./img/kb-9.png)  

8. Next, we are going to configure an Upload files data source.  
Firstly, download [bankingFAQ.docx](./doc/bankingFAQ.docx) and save it to your local server.  
Go back to the Data sources page, and click **Add data source**.  
This time we select **Upload files**. Click **Choose files** to upload the file. Then click **Upload**
![kb-10](./img/kb-10.png)  

9. Once done, navigate the application detail page. Under *Index* tab, check if the document count is *2*.  
![kb-11](./img/kb-11.png)  

10. For the last data source we are going to configure is an Amazon S3 data source.  
Before adding the data source, we are going to upload files into an S3 bucket.  
You can find the S3 url on [CloudFormation](https://console.aws.amazon.com/cloudformation) which you provisioned since [the infrastructure setup](../infra/README.md).  
![kb-12](./img/kb-12.png)  

Download the below files. And upload them on the S3 bucket.
- [Restaurant_Childrens_Menu.pdf](./doc/Restaurant_Childrens_Menu.pdf)
- [Restaurant_Dinner_Menu.pdf](./doc/Restaurant_Dinner_Menu.pdf)
- [Restaurant_week_specials.pdf](./doc/Restaurant_week_specials.pdf)

![kb-13](./img/kb-13.png)  
![kb-14](./img/kb-14.png)  
Click **Upload** and wait till it succeeded.  
![kb-15](./img/kb-15.png)  

11. Go back to the Data sources page, and click **Add data source**.  
Then we select **Amazon S3**, Give a data source name `restaurant-s3`.  
Select the IAM role containing with `-DataSourceRole-`.  
![kb-16](./img/kb-16.png)  

12. For **Sync scope**, in the field *Enter the data source location*, enter the name of your S3 bucket that you have just uploaded the files.  
Under **Sync mode**, select *Full sync*. 
![kb-17](./img/kb-17.png)  

---
**NOTE**

Amazon S3 connector support Amazon Q Business access control by configuring the ACL file in the data source configuration. The ACL file specifies which users and groups are allowed or denied to access particular documents or an S3 prefix / folder. Please check further on [AWS document](https://docs.aws.amazon.com/amazonq/latest/qbusiness-ug/s3-user-management.html).  

---

13. In **Sync run schedule**, select *Run on demand*. And click **Add data source**.  
![kb-18](./img/kb-18.png)  

14. After the data source was successfully created, click **Sync now** to start the sync, which takes up to 5-10 minutes.  
![kb-19](./img/kb-19.png)  

15. Once complete, go to the Data sources page. Now you have 3 data sources configured.  
Next we will chat with our knowledge bases via Amazon Q Business application.  
![kb-20](./img/kb-20.png)  

In [the next lab](../chat/README.md), we will try chatting with Amazon Q Business application.