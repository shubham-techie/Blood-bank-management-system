**Group Details**

Shubham Jaiswal – 1902060

Shubham Kadam – 1902066

Vedant Kangde – 1902069

**Blood Bank Management System**

**Description of Problem Statement**

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

**Requirement Specification**

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

**Architecture (ER) Diagram**

| ![](media/1a0afcf010b560eb4631e7898c1c6193.png) |
|-------------------------------------------------|

**Block Diagram**

![](media/b67008e6759cceca736eb4fd67a1b86f.png)

**Main Code/ Major Steps**

Phase I : Implementing Frontend and Backend

**Step 1**: Designing and Implementing the frontend using HTML, CSS & Bootstrap
and Javascript.

**Step 2**: Integrating the frontend with Django based web- framework backend to
run on server and sqlite3 database setup initially.

![](media/af85b3d423c1514cacc8a9ce35015bb2.png)

Phase II : Initializing Elastic Beanstalk

**Step 3**: Now, project is running properly on local server and we need to host
it on AWS cloud to make it available to users. We will be working with Elastic
beanstalk to deploy our webapp.

So, first installing **Elastic Beanstalk command line interface (EB CLI)** which
allows you to perform a variety of operations to deploy and manage your Elastic
Beanstalk applications and environments using your command prompt itself.

![](media/a27ecd11052e217feaf15103fd1e71be.png)

**Step 4**: Initializing Elastic Beanstalk inside the project root folder which
will create *.elasticbeanstalk / config.yml* setup file for deploying.

![](media/d7e2f29cdbeffa0658829cb24242f91b.png)

![](media/b93b7e72465600f43e4d12aa18829a5b.png)

Step 4: Next, creating the Elastic Beanstalk environment and deploying the
application.

![](media/498d1c669b7175d04054b4eab2c03d7d.png)

Now, our webapp has some *DNS CNAME*, which is basically URL of our website.

Phase III : Configuring the Environment

**Step 5**: Now, we will need to Configure the Environment i.e. some
configuration is to be done in our root folder so that Elastic Beanstalk can
locate our application and *settings.py* file.

Create file *.ebextensions/01_django.config* inside root folder.

![](media/a8e17f5fba4850df7157f3d902d8a58f.png)

**Step 6**: Also, *CNAME* which got created is to be added to the
*ALLOWED_HOSTS* in *settings.py* file.

![](media/9de766e99ebba9121a45a028d70ab054.png)

**Step 7**: Commit all the changes to git and deploy it.

![](media/e6cea95a0c0aa537346b35ea9de67827.png)

Finally, our website will be now running on URL (CNAME), but static css and js
files are not rendered properly.

Phase IV : Configuring AWS RDS with PostgreSQL Database Engine.

**Step 8** : Create Database with PostgreSQL in AWS RDS.

![](media/c7318b1d46af2fa0f7c9c1d534707d8d.png)

After creating RDS, check if the status is “*Available*”

![](media/de929a8916592552c1702d55bb5fac97.png)

**Step 9** : After the environmental update is done, EB will automatically pass
the some DB credentials to our Django app.

Now, adding these variables to our *DATABASES* in *settings.py* file.

![](media/3fac155cc281cc9355ae378cb29727d5.png)

**Step 10** : Next, we have to tell Elastic Beanstalk to run *makemigrations*
and *migrate* when a new application version gets deployed. So, adding these
containers in *.ebextensions/01_django.config file.*

![](media/e25209991580cb5b558b5a3cacc52d57.png)

**Step 11** : Still, admin is not created. So for that, make some *files* and
*folders* in *blood app*.

![](media/0425188298e7cb1b5801dd31bb0546f3.png)

![](media/ae49875e4915e318024cee633f2c8afd.png)

**Step 12** : Now again, we have to tell Elastic Beanstalk to run
*createsuperuser* when a new application version gets deployed. So, adding these
container in *.ebextensions/01_django.config file.*

![](media/91209e921aca5c52446eb17e1d15dcf1.png)

**Step 13** : Again, commit all the changes to git and deploy it, otherwise
Elastic Beanstalk won't detect the changes if we don't commit.

![](media/e6cea95a0c0aa537346b35ea9de67827.png)

At this stage, Blood Bank Management System webapp is deployed on AWS cloud with
Elastic Beanstalk and Database on AWS RDS.

![](media/dea4f2b0b9112f36c24d2afd1f8a87ff.png)

Phase V : Creating Amazon Simple Storage Service (S3) bucket for File Storage

**Step 14** : Creating a S3 Bucket

![](media/34db7ecff0ca4e167f2b02420585cd90.png)

**Step 15** : Creating an IAM group and user for S3 Bucket management.

User Group

![](media/0a1a93589096f35f543b574325785683.png)

User

![](media/291850ce8813f4bfd2eb5c077049f52c.png)

(AWS will generate authentication credentials for you. Download that .csv file)

**Step 16** : Setting Elastic Beanstalk S3 environment variables

![](media/dc246e5f3ac615f2d30816b92defe358.png)

**Step 17** : Configuring Django Static and Media Settings.

Next, in order for Django to communicate with our S3 Bucket, we need to install
the *django-storages* and *boto3* packages.

![](media/50ceb518cc373e0388fdb4c79a0e3d4d.png)

Next, add the newly installed app to *INSTALLED_APPS* in *settings.py*

![](media/74fa03c9c24fe615081fd8ebcb920474.png)

Configure django-storages to use the environmental variables passed by Elastic
Beanstalk.

![](media/cbe6b8c344ed9710d1e3e85f264d57a3.png)

Lastly, we need to run the *collectstatic* command after deployment is complete,
so add the container to the bottom of *.ebextensions/01_django.config*

![](media/d22c2692862c1794f17cfa0b58e79821.png)

Commit the changes to git and deploy

![](media/e6cea95a0c0aa537346b35ea9de67827.png)

Now, our Static files got uploaded on S3 bucket.

![](media/cbc2b3efa15aada2022fefd8292c21cc.png)

**  
**

**Screenshots**

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

**Conclusion**

So, Blood Bank Management System has been successfully designed, implemented and
hosted on Amazon Web services (AWS) Cloud Platform and is easily accessible to
users. The website is hosted on Elastic Beanstalk which internally creates EC2
instance. The project uses AWS services like Relational Database Service(RDS)
with postgresSql Engine to maintain database of Blood Stock and manage users. It
also uses Simple Storage Service (S3) buckets of AWS to store static files and
is managed using Internal Access Management (IAM) policy.
