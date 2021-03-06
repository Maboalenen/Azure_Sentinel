Azure-Sentinel
=========
<img width="166" alt="Screen Shot 2021-09-19 at 8 51 01 PM" src="https://user-images.githubusercontent.com/49055941/133937653-16cb31d4-adbf-4da7-8096-7e77f7b280ca.png">

Abstract
--------
 > Microsoft cloud-native security information event management (SIEM) and security orchestration automated response (SOAR)  
 > solution Investigate threats with artificial intelligence, and hunt for suspicious activities.
 > Data stored using log analytics,     
 > Query using: KQL Kusto Query Language (KQL).   
 > More details Azure_Sentinel overview <a href='https://docs.microsoft.com/en-us/azure/sentinel/overview' target='_blank'>Sentinel</a>   
 <img width="799" alt="Screen Shot 2021-04-17 at 4 51 32 PM" src="https://user-images.githubusercontent.com/49055941/115115439-2c7cf280-9f9d-11eb-9241-7300727e38d8.png">

    
    

Data Connectors (Collection)
-----
  > first need to connect to your security sources.Azure Sentinel comes with a number of connectors for Microsoft solutions  
  > you can your External solutions via API or External solutions via agent for on prem.  
  > More details <a href='https://docs.microsoft.com/en-us/azure/sentinel/connect-data-sources' target='_blank'>Data_connectors</a>   
<img width="610" alt="Screen Shot 2021-04-17 at 4 42 02 PM" src="https://user-images.githubusercontent.com/49055941/115115216-d9ef0680-9f9b-11eb-9aae-bd6ea8c2a991.png">


Workbooks
----
> workbooks to visualize your data within Azure Sentinel, something like. Dashboards,  
> you can use your built-in workbook, and you can edit or you can create your own.   
> More details <a href='https://docs.microsoft.com/en-us/azure/sentinel/tutorial-monitor-your-data' target='_blank'>Sentinel_Workbooks</a>   
 
<img width="716" alt="Screen Shot 2021-04-17 at 4 35 24 PM" src="https://user-images.githubusercontent.com/49055941/115115048-ecb50b80-9f9a-11eb-8840-14b17e305be8.png">

Analytics
---
> Create proactive analytics across your data, notified when something suspicious occurs.     
> You can enable built-in analytics alerts or built you own     
> You can also create custom, scheduled alerts from scratch.  
> more details <a href='https://docs.microsoft.com/en-us/azure/sentinel/tutorial-detect-threats-custom' target='_blank'>Analytics</a>    
 
<img width="1184" alt="Screen Shot 2021-04-17 at 5 01 55 PM" src="https://user-images.githubusercontent.com/49055941/115115724-a1046100-9f9e-11eb-9250-82c6a357a820.png">. 

Automation playbooks 
----
> Ability to respond to incidents automatically, you can automate some of your security operations and make your SOC more productive   
> **Note:** For automation playbooks like automatically creating incidents or sending email , you shoud create frist logic app.    
  
## Azure Logic Apps
> is a serverless, no-code solution for automating workflows. It integrates with hundreds of other services, making it a powerful solution for security orchestration, automation, and response (SOAR).  
> More details <a href='https://docs.microsoft.com/en-us/azure/sentinel/tutorial-respond-threats-playbook' target='_blank'>Automation playbooks </a>    
 
![Screen Shot 2021-04-17 at 10 13 44 PM](https://user-images.githubusercontent.com/49055941/115124323-2fdaa300-9fca-11eb-913a-bb5aa1ea7d65.png)

