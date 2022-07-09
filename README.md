# Blood Bank Management System
(DEMO Website)
#### Deployed on AWS with Elastic Beanstalk environment and RDS and S3 buckets.
#### URL : http://bloodbankmanagement-dev.ap-south-1.elasticbeanstalk.com/

### Description of Problem Statement

With an increase in the population, there is an increase in the need for blood.
The growing population of the world results in a lot of potential blood donors.
But in spite of this, not more than 10% of the total world population
participates in blood donation. With the growing population and the advancement
in medical science, the demand for blood has also increased. Due to the lack of
communication between the blood donors and the blood recipients, most of the
patients in need of blood do not get blood on time and hence they may lose their
lives. There is a dire need for synchronization between the blood donors and
hospitals and the blood banks. This improper management of blood leads to
wastage of the available blood inventory.

The proposed system (Blood Bank Management System) is designed to help the blood
bank administrator to meet the demand of blood by sending and/or serving the
request for blood as and when required. The proposed system gives the procedural
approach of how to bridge the gap between recipient, donor, and blood banks.
This application will provide a common ground for all the three parties (i.e.
recipient, donor, and admin) and will ensure the fulfillment of the demand for
blood requested by the recipient and/or blood bank.

Blood Bank Management System is a Web-based application that is designed to
store, process, retrieve and analyze information concerned with the
administrative and inventory management within a blood bank. This project aims
at maintaining all the information about blood donors, different blood groups
available in each blood bank and help them manage in a better way. Project Aim
is to provide transparency in this field, make the process of obtaining blood
from a blood bank hassle-free and corruption-free and make the system of blood
bank management effective. The main aim of developing this system is to provide
blood to the people who need blood.

### Requirement Specification

The ‘BLOOD BANK MANAGEMENT SYSTEM’ project is to interconnect all the blood
banks, hospitals, donors into a single network, validation, store various data
and information of blood of each individual. This system is used to store data
over a centralized server which consists of database where the individual’s
information cannot be accessed by a third party.

Technologies used in project are :

-   **Frontend** : HTML, CSS & Bootstrap, Javascript

-   **Backend** : Django python-web-framework

-   **Database** : AWS Relational Database Service (RDS) with PostgreSQL
    database engine.

-   **Deployed on** : AWS Elastic Beanstalk environment (EB) with Simple Storage
    Service(**S3**) buckets service to store static files. 
    

**Blood Bank Management System has three main module** –

**Donor** :

-   Donor can create account by providing basic details.

-   After Login, Donor can donate blood which is approved by admin and then the
    blood will be added to blood stock.

-   Donor can see their donation history with status (Pending, Approved,
    Rejected).

-   Donor can also request for blood from blood stock and see their blood
    request history.

**Patient** :

-   Patient can Create account and After Login, Can see number of blood request
    Made, Approved, Pending, Rejected by Admin on their dashboard.

-   Patient can request for blood of specific blood group and unit from blood
    stock.

-   Patient can see their blood request history with status (Pending, Approved,
    Rejected).

**Admin** : can –

-   View and Update each blood group from Blood Stocks

-   View, update, delete onors and Patients

-   Approves or Rejects the Blood donation request by Donor

-   Approves or Rejects the blood need requests by Patient as well as Donor.

### Architecture (ER) Diagram

| ![](media/1a0afcf010b560eb4631e7898c1c6193.png) |
|-------------------------------------------------|

### Block Diagram

![](media/b67008e6759cceca736eb4fd67a1b86f.png)

### Steps to setup AWS elastic beanstalk and RDS

#### Phase I : Implementing Frontend and Backend
#### Phase II : Initializing Elastic Beanstalk
#### Phase III : Configuring the Environment
#### Phase IV : Configuring AWS RDS with PostgreSQL Database Engine.
#### Phase V : Creating Amazon Simple Storage Service (S3) bucket for File Storage

### Screenshots

Home page

![](media/8eaffc80396f70895162e5c81ad83d22.png)

Sign in page for Donor

![](media/b1ee4f50811f85359fce12d56f5e91fa.png)

Donate Blood form for Donor

![](media/1ac31a80efd1d1a33b0d087adac9cd8c.png)

Donation history page of Donor

![](media/5390c399841df699bec59924d7f5aa72.png)

Blood request form for Donor

![](media/0480b745348a7b34ad08d8bec9a17732.png)

Blood request history page for Donor

![](media/1cefb9c11c4ebf7f6a6f3c3ea54f3083.png)

Patient signup page

![](media/0a2cea307759ff2c53c51d0db0988107.png)![](media/6a9615db57124295d43ee6b954306801.png)

Blood request form for patient

![](media/77c51e32bbe01d432c9c8d55152d3a6f.png)

Blood request history page for Patient

![](media/1a4b51131325616c84cb93ee5f2f17f1.png)

Dashboard for patient

![](media/d8a961874013130547ed50eb1eb66caa.png)

Sign in page for admin

![](media/9011b56c6ebb80e5522ee5d881e5d4f0.png)

Admin Dashboard of blood stock

![](media/1f74db81bf96a3b9a2ae9adc0d217971.png)

Admin Dashboard showing Donor’s Profile

![](media/980233747889cd5cea406787d65a9d75.png)

Admin Dashboard showing Patient’s Profile

![](media/a69f427379f154ea71736950db924f38.png)

Admin dashboard showing blood donation details

![](media/f17826b4fc455117d94907509a12f87d.png)

Admin dashboard showing blood request details

![](media/8396b47c671aefa1da001629da2ef73c.png)

Admin dashboard showing blood request history

![](media/bead82c35045770213669281384b2375.png)

Admin Dashboard to update blood stock

![](media/7bae7a325555246b7d77be7b98993ff3.png)

Logout page

![](media/51d76b8928bafd3d2755a423280a57f7.png)

### Conclusion

So, Blood Bank Management System has been successfully designed, implemented and
hosted on Amazon Web services (AWS) Cloud Platform and is easily accessible to
users. The website is hosted on Elastic Beanstalk which internally creates EC2
instance. The project uses AWS services like Relational Database Service(RDS)
with postgresSql Engine to maintain database of Blood Stock and manage users. It
also uses Simple Storage Service (S3) buckets of AWS to store static files and
is managed using Internal Access Management (IAM) policy.

### Reference
[AWS Elastic beanstalk setup guide](https://testdriven.io/blog/django-elastic-beanstalk/#s3-for-file-storage) 

**Credits** : [@sumitkumar1503](https://github.com/sumitkumar1503) for opensourcing [bloodbankmanagement](https://github.com/sumitkumar1503/bloodbankmanagement.git) project
