# Bulk PCF capture upload

PCF capture is done in 2 steps.  
•	Upload request for a PCF data  
•	Upload a PCF data.

# Exercise 1: Upload request for a PCF data 
Prepare the template for PCF request  
Load the PCF supplier data from below template 
CSV template link: Envizi-SCI-request-PCF.csv 

<img src="Images/Image26.jpg">

# Sample data shown below  
<img src="Images/Image27.jpg">

# Procedure 
1.	In the side navigation menu, expand Management and then select Job management. 
2.	Click New Job. 
3.	Select Import data and click Next. 
4.	Click Add file and upload the Envizi-SCI-request-PCF.csv file. 
5.	From the list of data mappings, select Supplier request - PCF (supplierRequestPcf).

 <img src="Images/Image28.jpg">

6.	Click Next and review the information. 
7.	Click Import. 
The following message appears. 
New import job created Job {Job ID} has been successfully created. 
8.	See the status of your import job on the Job Management page. 
Note: Depending on the size of the file, the import process might take some time to complete. 
If the status of your import job is Completed, then your data import job is successful. 
If the status of your import job shows CompletedWithErrors or Rejected,complete the following steps: 
a.	Click the Job ID and check the errors in the Job details section. 
b.	If errors are listed, then correct the highlighted errors in your CSV file and upload it again. 
c.	If errors are not listed, then click Retry the import and check the status after a brief period. 
Data loaded successfully
 <img src="Images/Image29.jpg">
Exercise 2: Upload a PCF data 
Prepare the template for the compliance record. The template is available in below link CSV template link: Envizi-SCI-supplier-PCF.csv
 <img src="Images/Image30.jpg">

Sample data is shown below  
<img src="Images/Image31.jpg">
Procedure 
1.	In the side navigation menu, expand Management and then select Job management. 
2.	Click New Job. 
3.	Select Import data and click Next. 
4.	Click Add file and upload the Envizi-SCI-supplier-PCF.csv file. 
5.	From the list of data mappings, select Supplier data - PCF (supplierDataPcf). 

<img src="Images/Image32.jpg">

6.	Click Next and review the information. 
7.	Click Import. 
The following message appears. 
New import job created Job {Job ID} has been successfully created. 
8.	See the status of your import job on the Job Management page. 
Note: Depending on the size of the file, the import process might take some time to complete. 
If the status of your import job is Completed, then your data import job is successful. 
If the status of your import job shows CompletedWithErrors or Rejected,complete the following steps: 
a.	Click the Job ID and check the errors in the Job details section. 
b.	If errors are listed, then correct the highlighted errors in your CSV file and upload it again. 
c.	If errors are not listed, then click Retry the import and check the status after a brief period. 
9.	Compliance record is the object which gets loaded here successfully 

<img src="Images/Image33.jpg">

Load new transaction data  
 
1.	Get the orderline transactions data Get the file Envizi-SCI-transaction-Order line_INBank_PCF_New.csv shared in the lab files  
2.	The file looks like below 
 
 <img src="Images/Image34.jpg"> 
 
3.	Navigate to Job Manager to ingest the orderlines 
4.	Create New import job  
5.	Add file and select the file - Envizi-SCI-transaction-Order line_INBank_PCF_New.csv 6. Important step: Select ‘Transaction data - Order Line ‘ under Data mapping 
7.	Click Next and Import the file.  
8.	Once file is processed and completed, navigate to Emission management 
Verify the supplier -specific emission  
Navigate to the emission management 
Observe the supplier-specific method
 <img src="Images/Image35.jpg">

Exercise 3: Update the Emission calculations of existing transactions   
However, there may be scenarios where an organization needs to apply the newly loaded custom factors to previously ingested transactions as well. This is often necessary to ensure consistency and accuracy in historical emissions data. 
In this exercise, we will walk through the steps required to recalculate emissions for existing transactions using the updated custom emission factors 
1. Export the existing order lines as shown below 

  <img src="Images/Image36.jpg">

   <img src="Images/Image37.jpg">

 1. Reimport the exported files .

  <img src="Images/Image38.jpg">

  Verify the supplier -specific emission  
  Navigate to the emission management 
  Observe the supplier-specific method  
 
  The supplier specific calculation can be viewed for the already loaded order lines. 

   <img src="Images/Image39.jpg">

