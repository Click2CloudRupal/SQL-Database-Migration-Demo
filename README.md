# SQL Database Migration Demo  

[About this demo](#about-this-demo)

[Part 1: Data Migration Assistance](#part-1-data-migration-assistance)

[Part 2: ](https://github.com/SpektraSystems/Azure-MySQL-DMS-Lab/blob/master/Module%202:%20Migrate%20MySQL%20to%20Azure%20Database%20for%20MySQL%20online%20using%20DMS.md)

## About this demo  

The way people consume books has changed, with audiobooks and digital downloads transforming the publishing industry. Nod Publishers wants to migrate their on-premises SQL 2008 R2 workload to the cloud. With this cloud transformation they can upscale user experience with the latest and greatest of cloud technologies. Nod Publishers is a digital platform that offers unlimited audiobooks and digital downloads to avid readers. Powered by Microsoft Azure, the Nod Publisher subscription platform uses advanced analytics to provide subscribers with personalized recommendations based on their interests—and it’s seen 100 percent growth year on year. This demo is based on the real customer scenario.  

### Goal  

The goal of this demo is to introduce SQL Server migration using Data Migration Assistance (DMA). In the second part of the demo we will publish our assessment to the Azure Migration Project. In the third part, we will estimate the Azure workloads cost per the SKU recommendations generated by DMA CLI.

# PART 1: Data Migration Assistance  

1. Connect to the virtual machine using the credentials provided in the lab details page.  

<img src="/images/lab-details-page.png">   

2. Open the **SQL Server Management Studio** as shown below:  

<img src="/images/sqlmgmtstudio-select.png">   

3. Connect to SQL Instances. In the Connect to Server window from the Server name dropdown select SQLSERVER-01 (default sql instance).    

4. Select **Windows Authentication** in the Authentication dropdown.  

5. Click the **Connect** button to connect to the instance.  

<img src="/images/sqlserver-connect-ssms.png">   

6. In Object Explorer, expand the Database nodes corresponding to the loaded instance.  

<img src="/images/databases-loaded.png">   

7. Go to the Desktop, open **Microsoft Data Migration Assistant**      

<img src="/images/click-dma-icon.png">    

8. In Data Migration Assistant, click on **+** to start a new Migration project.   

9. Enter Project name: **Migration Demo** (User defined field so feel free to use any name you like).    

10. Select **SQL Server** from the **Source server type** drop down (Articulate or talk about the support for AWS RDS for SQL Server workloads)    

11. Select **Azure SQL Database Managed Instance** from the **Target server type** drop down.  

12. Click on **Create**.  

<img src="/images/enter-dma-details-01.png">  

13. Check **Check database compatibility** option.  

14. Check **Check feature parity** option.   

15. Once selected click **Next**. 

<img src="/images/select-report-type.png">  

16. For Server name, type the Source SQL server: **sqlserver-01** (that we connected to in step 4)  
17. In Authentication type, select **Windows Authentication**.
18. In Connection properties: Check: Encrypt Connection Check: Trust server certificate   
19. Click **Connect**.  

<img src="/images/connect-to-server-dma.png">  

20. In **Add sources** pane: Select the first 35 databases, starting from **Accomodation X** and the last database to be selected being  **Innovation X-HR**.  

21. Click on **Add**.  

<img src="/images/first35databases.png">  

22. Click **Start Assessment**  

<img src="/images/start-assesment-mi.png">  

23. Select **SQL Server feature parity**  

24. Select/Expand Unsupported feature.  

25. Point to the **Impact and generated recommendations**.  

<img src="/images/sqlserverparity-mi.png">  

26. Switch to the **Compatibility issues**.  

27. Toggle between databases to see Compatibility issues.  

28. Select **Adventure Work Associates** database.  

29. Select/Expand Migration blocker.  

30. Point to the **Impact and generated recommendations**.  

31. Click on **Upload to Azure Migrate** button.  

<img src="/images/compatibilityissues-mi.png">     

32. You will be asked to login to your azure account. Sign in to your Azure Account using the credentials provided in the lab details page:  

<img src="/images/azure-credentials.png">  

33. Select the appropriate **Subscription** and the **Migration Project**.  

<img src="/images/upload-azure-migrate-mi.png">  









