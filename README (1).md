# Project Title
MIST 4610 Group Project 1

## Team Name
39217 Group 7

## Team Members
Dylan McMorrow [@DylanMcMorrow] (https://github.com/dylanmcmorrow5/MIST4610GroupProject1/blob/main/README.md) 
Aafreen Anjum [@AafreenAnjum](https://github.com/aanjum2003/healthcare/blob/main/README%20(1).md)
Jack Drummond [@JackDrummond](https://github.com/jdrum7/MISTproject)
Ishi Gupta [@IshiGupta](https://github.com/ishigupta24/healthcare/blob/main/README%20(1).md)
Miral Lakhani [@MiralLakhani](https://github.com/mirLakhani/healthcare1)

## Problem Description
Our primary goal is to create a relational database that significantly improves the efficiency and quality of a medical center's operations. The central entity in our database model is the "Visit Entity," representing each medical patient's visit. This "Visit Entity" is intricately linked with other key components, including the "Patient," "Visit Record," "Physician," "Room," and "Billing" entities. Our focus is on accurately modeling these relationships, generating realistic sample data, and populating these entities with relevant attributes.

Moreover, we aim to implement fully functional query capabilities on this data. These queries will not only facilitate day-to-day operations but also yield valuable business insights into the medical center's functioning. This enhanced database will provide us with a comprehensive and detailed view of patient visits, medical records, physician-patient interactions, room allocation, and billing processes. By effectively leveraging this database, we can drive informed decision-making, streamline operations, and ultimately enhance the overall performance and quality of care within the medical center.

We have attached screenshots from the initial conversation with our client. As evident in our data model below, we adjusted some of the entities originally proposed by our client to better suit their needs and boost efficiency.

<img width="622" alt="Screen Shot 2023-11-03 at 6 11 27 PM" src="https://github.com/ishigupta24/healthcare/assets/148798025/6373864f-d338-464d-8d33-944f4ab412ee">

<img width="614" alt="Screen Shot 2023-11-03 at 6 12 14 PM" src="https://github.com/ishigupta24/healthcare/assets/148798025/5635a711-81ce-4ba9-b7c4-d623db2ddcc3">

<img width="610" alt="Screen Shot 2023-11-03 at 6 12 39 PM" src="https://github.com/ishigupta24/healthcare/assets/148798025/ea777e46-3fd8-4465-bf24-72c7835d2e78">


## Data Model Explanation
Our model is designed to represent the structure of a small to medium sized emergency healthcare clinic. The Patient entity stores information about all patients who come to the clinic to seek medical care, such as their name, contact information, and any relevant allergies to medications. Each patient will have one or more emergency contacts listed, which is represented by the 1 to many relationship between the Patient and Contact entities. The Contact table stores information about each emergency contact such as their name, address, phone number, email, and the relationship to the patient (e.g. mother, aunt, etc.).

We then have the Visit entity, which is central to the entire model. The Visit table is updated each time a patient comes to the front desk and fills out paperwork, regardless if any tests were performed. Each patient can have as many visits as needed, which is represented by the 1 to many relationship between the Patient and Visit entities. A visit is also associated with a particular physician, whose information is stored in the Physician table. Every visit is associated with one patient and one primary physician. A physician will have many visits over the course of their career, but each visit only has one physician, which can be seen by the one to many relationship between Physician and Visit.

Each visit also takes place in a particular room. Information about each room such as its number, name, and the wing it is located in (North, South, East, or West) is stored in the Room entity. Each visit is associated with one room, but a particular room will be associated with many visits, which can be seen in the one to many relationship between Room and Visit. It is important to note that while a patient may have tests done in multiple rooms on the same visit (X-ray in one room, MRI in another), each visit is assigned a primary room number where the Physician meets with them privately. 

The clinic also owns a lot of different pieces of medical equipment. Information about this equipment is stored in the Equipment table. The table stores the name of the equipment (e.g. an X-Ray machine), the date the equipment was purchased, and also the price. Additionally every piece of equipment is associated with a particular room. One room can have multiple pieces of equipment, but a particular piece of equipment can only belong to one room. This is shown by the one to many relationship between Room and Equipment. 

Additionally, the clinic can perform many different tests. The Test entity stores information about the different types of medical tests done on a patient. Examples include blood tests, MRIs, etc., and the visitRecord entity stores information about each visit and any potential tests performed. There is a one to many relationship between visitRecord and Test because a particular test can be done multiple times on the same patient, and therefore be found in multiple different visit records. There is also a one to many relationship between Visit and visitRecord because during each visit a patient can have multiple tests performed on them, which will each go into a separate visit record.

Each Visit is associated with one bill (also known as an invoice). This is represented by the one to one relationship between the Visit and Billing tables. While each visit can be associated with multiple visit records, it is important to note that a visit can only have one bill in total, regardless of the number of visit records associated with one visit. 

Each visitRecord then has the potential to generate a Prescription for the patient. One visitRecord can generate multiple prescriptions (E.g. a test revealing a broken bone may lead to multiple pain relief medications prescribed), and each prescription is only tied to one visitRecord. This is evident by the one to many relationship between visitRecord and Prescription. 

This clinic also stores many different medications, which we have organized in the Medications table. The clinic also maintains a list of approved suppliers for which they get their medications from. At this particular clinic, each medication is provided by only one supplier. This is represented by the one to many relationship between the Supplier and Medication tables, as one supplier can provide different medications, but each medication is tied to a particular supplier. Each prescription can only have one medication listed on it. That being said, a particular medication can be listed in multiple different prescriptions. This is evident in the one to many relationship between Medications and Prescriptions.

## Data Model Screenshot
<img width="1015" alt="Screen Shot 2023-11-03 at 5 39 53 PM" src="https://github.com/ishigupta24/healthcare/assets/148798025/ae3fe5b6-fdd1-46ae-8c07-0873d89e8e85">

## Data Dictionary Screenshots
<img width="644" alt="Screen Shot 2023-11-03 at 5 45 26 PM" src="https://github.com/ishigupta24/healthcare/assets/148798025/2cc357d8-0df3-47f9-ba96-de656f54826d">
<img width="660" alt="Screen Shot 2023-11-03 at 5 45 44 PM" src="https://github.com/ishigupta24/healthcare/assets/148798025/616f7641-f146-40fc-b9e4-2cc2429bad0a">
<img width="690" alt="Screen Shot 2023-11-03 at 5 45 57 PM" src="https://github.com/ishigupta24/healthcare/assets/148798025/f669b38a-579a-4d32-8a76-6fa31e55541a">
<img width="668" alt="Screen Shot 2023-11-03 at 5 46 08 PM" src="https://github.com/ishigupta24/healthcare/assets/148798025/e1f11d7b-c452-420a-9256-318420d55a04">
<img width="667" alt="Screen Shot 2023-11-03 at 5 46 14 PM" src="https://github.com/ishigupta24/healthcare/assets/148798025/e269b8d9-00d1-4111-8e07-482c2ae2987e">
<img width="655" alt="Screen Shot 2023-11-03 at 5 46 32 PM" src="https://github.com/ishigupta24/healthcare/assets/148798025/8278884a-29ec-4e93-872a-47564d0f211f">
<img width="614" alt="Screen Shot 2023-11-03 at 5 46 41 PM" src="https://github.com/ishigupta24/healthcare/assets/148798025/fc31f8a6-85d9-42d9-b1bc-98ef6e9f4106">
<img width="664" alt="Screen Shot 2023-11-03 at 5 46 50 PM" src="https://github.com/ishigupta24/healthcare/assets/148798025/1e31f4d1-517c-4455-ba80-22d7a799a5cd">
<img width="642" alt="Screen Shot 2023-11-03 at 5 48 10 PM" src="https://github.com/ishigupta24/healthcare/assets/148798025/8000d307-2cbf-4165-8165-f8b11268930f">
<img width="661" alt="Screen Shot 2023-11-03 at 5 48 20 PM" src="https://github.com/ishigupta24/healthcare/assets/148798025/c66eefc7-2250-4bfc-a67b-e66a3dadf0e3">
<img width="667" alt="Screen Shot 2023-11-03 at 5 48 30 PM" src="https://github.com/ishigupta24/healthcare/assets/148798025/3dac3dd9-5de1-4e5c-a36f-721b10bf45b9">
<img width="658" alt="Screen Shot 2023-11-03 at 5 48 41 PM" src="https://github.com/ishigupta24/healthcare/assets/148798025/15d160ff-8b71-41c8-b9d4-51c3449b6eb3">



## Query Matrix
<img width="647" alt="Screen Shot 2023-11-03 at 5 49 21 PM" src="https://github.com/ishigupta24/healthcare/assets/148798025/3bbf023c-f6bb-4ef1-8107-9e0366ad807a">
 
Query 1:

Query 1 lists the equipment ID and name of equipment that is not currently assigned to a room.
<img width="632" alt="Screen Shot 2023-11-03 at 6 04 17 PM" src="https://github.com/ishigupta24/healthcare/assets/148798025/98bceba3-3d6d-40ca-93f5-bb1d66afbb63">


The provided query is essential for management to identify equipment that is not currently assigned to any room, enabling efficient resource allocation and cost control. It would help managers identify which equipment could be allocated into rooms to ensure that they are maintaining operational efficiency within the medical center.

Query 2:

Query 2 lists physicians’ names who did not have any visits on April 29, 2023.
<img width="619" alt="Screen Shot 2023-11-03 at 6 05 24 PM" src="https://github.com/ishigupta24/healthcare/assets/148798025/af7304f6-25e1-4b6e-971f-6179e9e2dd61">


This query can allow managers to quickly identify which physicians did not see any patients on a particular day. This provides information that will be useful when they are scheduling the physicians for the upcoming weeks. The insights we derive from this query will help managers fine tune each physician’s schedule which is important for the overall success of the medical center.

Query 3:

Query 3 lists all physicians and the total number of visits they have conducted.
<img width="621" alt="Screen Shot 2023-11-03 at 6 05 41 PM" src="https://github.com/ishigupta24/healthcare/assets/148798025/98117867-9bf7-4fb3-acb8-c0c39451e091">


This query allows managers to monitor physician progress and could be used for Employee of the Week purposes. This would also enable managers to assess the productivity and contributions to patient care of the physicians.By tracking how frequently physicians have patient visits and identifying any underperformance and potential discrepancies.

Query 4:

Query 4 calculates the average price of equipment in each room.
<img width="620" alt="Screen Shot 2023-11-03 at 6 06 04 PM" src="https://github.com/ishigupta24/healthcare/assets/148798025/57ceea0d-2922-4ede-a6aa-88701c5bcefa">


Query 4 allows the clinic managers to see which rooms they have invested the most money into for equipment, and which rooms they have invested the least in. It gives an idea of which rooms could use further investment in equipment in order to improve the care and treatment for patients.

Query 5:

Query 5 lists the patients with a total billing amount exceeding 3000 dollars.
<img width="621" alt="Screen Shot 2023-11-03 at 6 07 32 PM" src="https://github.com/ishigupta24/healthcare/assets/148798025/3057b126-dca2-42d2-8c37-0ade1a3befc8">


Query 5 enables clinic managers to find which patients have spent $3000 or more on a single bill for a visit, in case the the managers would like to decide to give a future discount or rebate to those patients.

Query 6:

Query 6 lists the patient names and the number of visits they have whose status is not ‘Canceled’.
<img width="621" alt="Screen Shot 2023-11-03 at 6 07 52 PM" src="https://github.com/ishigupta24/healthcare/assets/148798025/c9758177-babf-4f8d-b69a-a0e1505393fc">


Query 6 permits clinic managers to identify the number of visits a patient has scheduled and actually attended. Canceled appointments are frequent occurrences for clinics. Therefore it is important for managers to have the ability to omit them when finding the number of appointments a patient has had.

Query 7:

Query 7 displays the name (last name and first name concatenated) of the physician and the amount of billing he has generated. Order results in a descending value of dollars’ worth of billing.
<img width="617" alt="Screen Shot 2023-11-03 at 6 08 20 PM" src="https://github.com/ishigupta24/healthcare/assets/148798025/8ca9109f-d8c1-4e5b-bc78-161b9f5d0039">


Query 7 grants the clinic the capability to find the total billing amount each doctor has generated. There are numerous reasons this is valuable. For instance, a physician could be overcharging patients accidentally, or maybe the clinic is interested in seeing the physicians who have produced the most revenue so that the clinic can give them a salary bonus.

Query 8:

Query 8 lists the five suppliers that have supplied the most medications, and the number of medications have they have supplied.
<img width="622" alt="Screen Shot 2023-11-03 at 6 08 39 PM" src="https://github.com/ishigupta24/healthcare/assets/148798025/94cc62be-46b4-4c18-b487-b99f05b7585b">


Query 8 also offers a valuable overview of the suppliers that have consistently provided the highest number of medications, allowing managers to make informed decisions regarding supplier relationships, when to negotiate better terms, and to enhance the clinic's overall medication inventory management.

Query 9:

Query 9 lists the visit with the highest number of tests performed.
<img width="625" alt="Screen Shot 2023-11-03 at 6 09 00 PM" src="https://github.com/ishigupta24/healthcare/assets/148798025/fe7641d5-67f9-4988-8bed-a68d8248fd90">


Query 9 allows managers to identify the highest amount of tests conducted during one visit. Perhaps they are considering adding an additional charge if a certain number of tests are conducted, and they wish to see the largest number in order to help them make a more informed decision.

Query 10:

Query 10 lists the number of bills of each patient with an amount that is greater than their own average bill amount
<img width="623" alt="Screen Shot 2023-11-03 at 6 09 23 PM" src="https://github.com/ishigupta24/healthcare/assets/148798025/a329f8ec-349f-4f54-8f0e-29e6de14eb6f">


Query 10 allows the clinic staff to give more detailed information on billing to their patients. A patient who has had numerous visits may want to know the number of visits that have exceeded the average billing amount of one of their own visits.

## Database Information
Name of Database: ns_F2339217Group7
