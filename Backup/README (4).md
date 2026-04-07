# envizi_sci-emission-mgmt
 
 
 
 
# Data model introduction 
Envizi Supply Chain Intelligence is built on an IBM operational data processing system that uses a structured, normalized, canonical data model. Envizi-SCI is a self-configuring system based on this canonical data model  which means that when data is ingested in the correct formats, the user experiences and operational flows become available. Envizi-SCI is also streamprocessing based, which means that data is continuously ingested and made available. 
 
Envizi-SCI contains many admin-accessible utilities for browsing the schema, viewing samples, and more in the Data management section of the application. This guide will help you as an administrator of the system to understand the structure of the data model and give you insight into how to best structure your data to populate all functionality. Please refer to the Envizi-SCI Data Model for more detailed information. 

<img src="Images/Image1.jpg">
  
This partial data model shows the most important normalized files in the model. Organization, 
Product, Location, and Catalog are master data which typically do not update often. Order and Orderline data are transactional records which can be sent into Envizi-SCI either periodically or on a regular basis. Note that there are many fields available in the model, but the partial relationship diagram above shows only the important subset of data. 
 
You will note that each object type has a set of field marked as identifiers. When loading data into the system in CSV form. it is critical to select values for these identifier fields which define unique records. During ingest processing, identifiers are reconciled between objects, effectively creating joins. 
Note : The loading of data in job manager takes a little while . We can check the status in View objects for this job(Open in Graphiql) to see if it is loaded correctly by checking the number of rows in the GraphQL 
 <img src="Images/Image2.jpg">

 
# Load Data using the Envizi SCI standard templates 
Templates are pre-designed data maps that facilitate the automation of data mapping in the data import process. Before uploading data into the Envizi Supply Chain Intelligence, you must convert client de-normalized data into the templates. 
The following table lists all templates, defines their uses, the topics where they are referenced, and indicates when each template is used. 
# 1. Get the Template 
Get the template excel template from below link 
https://www.ibm.com/docs/en/envizi-supply-chain?topic=configuring-templates-overview 
<img src="Images/Image3.jpg">

 
# 2. Understand the template (Optional) 
Let us understand about this template. 
If you want to prepare the template with your own data then only this section is required. Otherwise directly you can skip this and go to next section. 
# 2.1 The template 
The content of the template looks like the following. 
 
# Loading Master data 
# 2.1.2 Setting up products 
The products data defines purchased goods and services, which are essential for emissions calculations. Set up products during initial system configuration and update as necessary to reflect ongoing changes. 
Download the following CSV template and enter your company's data. Verify that all the required values are entered. 
CSV template link: Envizi-SCI-master-Product.csv 
The following table outlines the required headers and associated information for preparing the CSV file. You have the flexibility to ignore recommended and optional values, as needed. 
<img src="Images/Image4.jpg">

 
Sample data shown below 
<img src="Images/Image5.jpg">

 
# Procedure 
1.	In the side navigation menu, expand Management and then select Job management. 
2.	Click New Job. 
3.	Select Import data and click Next. 
4.	Click Add file and upload the Envizi-SCI-master-Product_INBank.csv file. 
5.	From the list of data mappings, select Master data - Product (masterDataProduct). 
<img src="Images/Image6.jpg">

 
6.	Click Next and review the information. 
7.	Click Import. 
The following message appears. 
New import job created Job {Job ID} has been successfully created. 
You might notice that uploading a single file result in the creation of multiple jobs in the Job Manager. This occurs because the mapping is linked to multiple business objects, which in turn triggers the submission of multiple jobs. To confirm that the upload completed successfully, you must verify that each job is completed without any errors. 
 
8.	See the status of your import job on the Job Management page. 
If the status of your import job is Completed, then your data import job is successful. 
If the status of your import job shows CompletedWithErrors or Rejected,complete the following steps: 
a.	Click the Job ID and check the errors in the Job details section. 
b.	If errors are listed, then correct the highlighted errors in your CSV file and upload it again. 
c.	If errors are not listed, then click Retry the import and check the status after a brief period. 
  
Created 2 objects -product and product supplier 
 <img src="Images/Image7.png">

 # 2.1.3 Setting up purchasing organizations 
The purchasing organization data defines a purchasing organization and hierarchy, which is used in reporting. Set up purchasing organizations during system configuration and update as necessary to reflect ongoing changes. 
Download the following CSV template and enter your company's data. Verify that all the required values are entered. 
CSV template link: Envizi-SCI-master-Purchasing organization.csv 
The following table outlines the required headers and associated information for preparing the CSV file. You have the flexibility to ignore recommended and optional values, as needed. 

<img src="Images/Image8.jpg">

 
Sample data  shown below 
<img src="Images/Image9.jpg">

 
# Procedure 
1.	In the side navigation menu, expand Management and then select Job management. 
2.	Click New Job. 
3.	Select Import data and click Next. 
4.	Click Add file and upload the Envizi-SCI-master-Purchasing_INBank.csv file. 
5.	From the list of data mappings, select Master data - Purchasing organization (masterDataPurchasingOrganization). 
<img src="Images/Image10.jpg">

 
6.	Click Next and review the information. 
7.	Click Import. 
The following message appears. 
New import job created Job {Job ID} has been successfully created. 
You might notice that uploading a single file result in the creation of multiple jobs in the Job Manager. This occurs because the mapping is linked to multiple business objects, which in turn triggers the submission of multiple jobs. To confirm that the upload completed successfully, you must verify that each job is completed without any errors. 
<img src="Images/Image11.jpg">

 
8.	See the status of your import job on the Job Management page. 
Note: Depending on the size of the file, the import process might take some time to complete. 
If the status of your import job is Completed, then your data import job is successful. 
If the status of your import job shows CompletedWithErrors or Rejected,complete the following steps: 
a.	Click the Job ID and check the errors in the Job details section. 
b.	If errors are listed, then correct the highlighted errors in your CSV file and upload it again. 
c.	If errors are not listed, then click Retry the import and check the status after a brief period. 
<img src="Images/Image12.jpg">

 
# 2.1.4 Setting up purchasing locations 
The purchasing location data defines all receiving locations of purchased goods and services in IBM® Envizi™ Supply Chain Intelligence. The location data is used in IBM Envizi ESG 
Suite account-based reporting by default, where all emissions data is aggregated by purchasing location. Set up purchasing locations during initial system configuration and update them as necessary to reflect ongoing changes. 
Download the following CSV template and enter your company's data. Verify that all the required values are entered. 
CSV template link: Envizi-SCI-master-Purchasing location.csv 
The following table outlines the required headers and associated information for preparing the CSV file. You have the flexibility to ignore recommended and optional values, as needed. 
Note: The location ID in Envizi Supply Chain Intelligence must match the location reference in Envizi ESG Suite. 
<img src="Images/Image13.jpg">

 
Sample data  shown below 
<img src="Images/Image14.jpg">

  
# Procedure 
1.	In the side navigation menu, expand Management and then select Job management. 
2.	Click New Job. 
3.	Select Import data and click Next. 
4.	Click Add file and upload the Envizi-SCI-master-Purchasing location_INBank.csv file. 
5.	From the list of data mappings, select Master data - Purchasing location (masterDataPurchasingLocation). 
<img src="Images/Image15.jpg">

 
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

<img src="Images/Image16.jpg">

 
# 2.1.1 Setting up suppliers 
The supplier data defines all suppliers of purchased goods and services, including country for emissions calculations and contact information for supplier portal communication. Set up suppliers during initial system configuration and update as necessary to reflect ongoing changes. 
Download the following CSV template and enter your company's data. Verify that all the required values are entered. 
CSV template link: Envizi-SCI-master-Supplier.csv 
<img src="Images/Image17.jpg">

 
Sample data shown below 
<img src="Images/Image18.jpg">

 
# Procedure 
1.	In the side navigation menu, expand Management and then select Job management. 
2.	Click New Job. 
3.	Select Import data and click Next. 
4.	Click Add file and upload the Envizi-SCI-master-Supplier_INBank.csv  file. 
5.	From the list of data mappings, select Master data - Supplier (masterDataSupplier). 
<img src="Images/Image19.jpg">

 
6.	Click Next and review the information. 
7.	Click Import. 
The following message appears. 
New import job created Job {Job ID} has been successfully created. 
You might notice that uploading a single file result in the creation of multiple jobs in the Job Manager. This occurs because the mapping is linked to multiple business objects, which in turn triggers the submission of multiple jobs. To confirm that the upload completed successfully, you must verify that each job is completed without any errors. 
<img src="Images/Image20.jpg">

 
 
 
8.	See the status of your import job on the Job Management page. 
Note: Depending on the size of the file, the import process might take some time to complete. 
If the status of your import job is Completed, then your data import job is successful. 
If the status of your import job shows CompletedWithErrors or Rejected,complete the following steps: 
a.	Click the Job ID and check the errors in the Job details section. 
b.	If errors are listed, then correct the highlighted errors in your CSV file and upload it again. 
c.	If errors are not listed, then click Retry the import and check the status after a brief period. 
Note : The loading of data in job manager takes a little while . We can check the status in View objects for this job(Open in Graphiql) to see if it is loaded correctly by checking the number of rows in the GraphQL 
 
Creates 3 jobs – Contact, Location, Organization 
<img src="Images/Image21.jpg">



 
# 2.1.5 Assigning product category factors 
Assigning product category factors involves defining the 3-level product categories and mapping the L3 category to the appropriate emissions factor ID. Assign product category factors during initial system configuration, and update as necessary to reflect ongoing changes. 
 
Download the following CSV template and enter your company's data. Verify that all the required values are entered. 
CSV template link: Envizi-SCI-master-Product mapping.csv 
 
The following table outlines the required headers and associated information for preparing the CSV file. 
<img src="Images/Image22.jpg">

 
Sample data  is shown below  
<img src="Images/Image23.jpg">

  
# List of factor codes 
You can view the list of factor codes from below link :- https://www.ibm.com/docs/en/envizi-supply-chain?topic=administering-creating-customfactors 
Procedure 
1.	In the side navigation menu, expand Management and then select Job management. 
2.	Click New Job. 
3.	Select Import data and click Next. 
4.	Click Add file and upload the Envizi-SCI-master-Product_INBank.csv file. 
5.	From the list of data mappings, select Master data - Product mapping (masterDataProductMapping). 
 
<img src="Images/Image24.jpg">

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
  
<img src="Images/Image25.jpg">

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




# Define Product Mapping

Product mapping links each product category to the right emission factor, so Envizi SCI can calculate emissions accurately for every product or service you buy.

**Why is it important?**
- Ensures each product is matched to the correct emission factor
- Makes your emissions reporting more accurate
- Helps you start with industry-standard factors (like EORA66) and improve over time
- You define your product categories (3 levels: L1, L2, L3)
- You map each L3 product category to an EORA66 emission factor code
- You can update these mappings as your data or methods improve

**What do you need to do?**
- Set up product category mappings when you first configure the system
- Review and update mappings as your business or reporting needs change
  
Lets look at the following sections on how INBank organization maps their product categories to appropriate emission factor codes.  Identifying and assigning spend-based emission factor code is currently manual process and our product is working towards automated classification using AI.

---

## 1. Get the Product Template

1. Copy the template file with the name *Envizi-SCI-master-Product mapping.csv* 

<div align="center">
  <img src="Images/SCI-master-productMapping.png">
</div>

2. Review the header columns and sample data. Detailed explanations for each column are provided [here](https://www.ibm.com/docs/en/envizi-supply-chain?topic=configuring-assigning-product-category-factors):

  - **Category L3 ID** (Required): The unique code for the third (lowest) level of your product hierarchy. This should match the `Category L3 ID` in your master Product file.

  - **Category L3 name** (Required): The name for the third level of your product hierarchy. Use clear names to help with searching and filtering in the SCI UI.

  - **Category L2 ID** (Required): The unique code for the middle level of your product hierarchy. This should match the `Category L2 ID` in your master Product file.

  - **Category L1 ID** (Required): The unique code for the top level of your product hierarchy. This should match the `Category L1 ID` in your master Product file.

  - **Emissions factor ID** (Required): The code for the emissions factor group to use for this product category. See the [Factor codes list]([https://](https://www.ibm.com/docs/en/envizi-supply-chain?topic=configuring-assigning-product-category-factors#assigning_product_category_factors__ph_bqc_n4h_m2c)) for allowed values 

  *Note: If you do not have a specific value for any category ID, use 'All'.*


==== Work further on the  ===========
## 2. Assigning product category factors 

Download the following CSV template and enter your company's data. Verify that all the required values are entered. 
CSV template link: Envizi-SCI-master-Product mapping.csv 

The following table outlines the required headers and associated information for preparing the CSV file. 
<img src="Images/Image22.jpg">

Sample data  is shown below  
<img src="Images/Image23.jpg">


# List of factor codes 
You can view the list of factor codes from below link :- https://www.ibm.com/docs/en/envizi-supply-chain?topic=administering-creating-customfactors 
Procedure 
1.	In the side navigation menu, expand Management and then select Job management. 
2.	Click New Job. 
3.	Select Import data and click Next. 
4.	Click Add file and upload the Envizi-SCI-master-Product_INBank.csv file. 
5.	From the list of data mappings, select Master data - Product mapping (masterDataProductMapping). 
 
<img src="Images/Image24.jpg">

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
  
<img src="Images/Image25.jpg">




# Data Modelling 

Envizi Supply Chain Intelligence is built on an IBM operational data processing system that uses a structured, normalized, canonical data model. Envizi-SCI is a self-configuring system based on this canonical data model  which means that when data is ingested in the correct formats, the user experiences and operational flows become available. Envizi-SCI is also streamprocessing based, which means that data is continuously ingested and made available. 

Envizi-SCI contains many admin-accessible utilities for browsing the schema, viewing samples, and more in the Data management section of the application. This guide will help you as an administrator of the system to understand the structure of the data model and give you insight into how to best structure your data to populate all functionality. Please refer to the Envizi-SCI Data Model for more detailed information. 

<img src="Images/Image1.jpg">
  
This partial data model shows the most important normalized files in the model. Organization, 
Product, Location, and Catalog are master data which typically do not update often. Order and Orderline data are transactional records which can be sent into Envizi-SCI either periodically or on a regular basis. Note that there are many fields available in the model, but the partial relationship diagram above shows only the important subset of data. 
 
You will note that each object type has a set of field marked as identifiers. When loading data into the system in CSV form. it is critical to select values for these identifier fields which define unique records. During ingest processing, identifiers are reconciled between objects, effectively creating joins. 
Note : The loading of data in job manager takes a little while . We can check the status in View objects for this job(Open in Graphiql) to see if it is loaded correctly by checking the number of rows in the GraphQL 
 <img src="Images/Image2.jpg">