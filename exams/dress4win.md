# [Dress4Win Case Study](https://cloud.google.com/certification/guides/cloud-architect/casestudy-dress4win-rev2)

## Business Requirements

 - Build a reliable and reproducible environment with scaled parity of production.
- Improve security by defining and adhering to a set of security and Identity and Access Management (IAM) best practices for cloud.
- Improve business agility and speed of innovation through rapid provisioning of new resources.
- Analyze and optimize architecture for performance in the cloud.

## Technical Requirements
- Easily create non-production environments in the cloud.
- Implement an automation framework for provisioning resources in cloud.
- Implement a continuous deployment process for deploying applications to the on-premises datacenter or cloud.
- Support failover of the production environment to cloud during an emergency.
- Encrypt data on the wire and at rest.
- Support multiple private connections between the production data center and cloud environment.

## Executive Statement
Our investors are concerned about our ability to scale and contain costs with our current infrastructure. They are also concerned that a competitor could use a public cloud platform to offset their up-front investment and free them to focus on developing better features. Our traffic patterns are highest in the mornings and weekend evenings; during other times, 80% of our capacity is sitting idle.

Our capital expenditure is now exceeding our quarterly projections. Migrating to the cloud will likely cause an initial increase in spending, but we expect to fully transition before our next hardware refresh cycle. Our total cost of ownership (TCO) analysis over the next 5 years for a public cloud strategy achieves a cost reduction between 30% and 50% over our current model.

---
# Exams
## Question 1
#### For this question, refer to the Dress4Win case study. 
At Dress4Win, an operations engineer wants to create a low-cost solution to remotely archive copies of database backup files. The database files are compressed tar files stored in their current data center. How should he proceed?

- [ ] A. Create a cron script using `gsutil` to copy the files to a Coldline Storage bucket.
- [ ] B. Create a cron script using `gsutil` to copy the files to a Regional Storage bucket.
- [ ] C. Create a Cloud Storage Transfer Service Job to copy the files to a Coldline Storage bucket.
- [ ] D. Create a Cloud Storage Transfer Service job to copy the files to a Regional Storage bucket.

> D
> Follow these rules of thumb when deciding whether to use `gsutil` or Storage Transfer Service:  
>
> 📌 When transferring data from an on-premises location, use `gsutil`.
>
> 📌 When transferring data from another cloud storage provider, use `Storage Transfer Service`.
>
> 📌 Otherwise, evaluate both tools with respect to your specific scenario. 
>
> Use this guidance as a starting point. The specific details of your transfer scenario will also help you
determine which tool is more appropriate

---
## Question 2
#### For this question, refer to the Dress4Win case study. 
Dress4Win has asked you to recommend machine types they should deploy their application servers to. How should you proceed?

- [ ] A. Perform a mapping of the on-premises physical hardware cores and RAM to the nearest machine types in the cloud.
- [ ] B. Recommend that Dress4Win deploy application servers to machine types that offer the highest RAM to CPU ratio available.
- [ ] C. Recommend that Dress4Win deploy into production with the smallest instances available, monitor them over time, and scale the machine type up until the desired performance is reached.
- [ ] D. Identify the number of virtual cores and RAM associated with the application server virtual machines align them to a custom machine type in the cloud, monitor performance and scale the machine types up until the desired performance is reached.

> D
---
## Question 3
#### For this question, refer to the Dress4Win case study.
Dress4Win has asked you for advice on how to migrate their on-premises MySQL deployment to the cloud. They want to minimize downtime and performance impact to their on-premises solution during the migration. Which approach should you recommend?

- [ ] A. Create a dump of the on-premises MySQL master server, and then shut it down, upload it to the cloud environment, and load into a new MySQL cluster.
- [ ] B. Setup a MySQL replica server/slave in the cloud environment, and configure it for asynchronous replication from the MySQL master server on-premises until cutover.
- [ ] C. Create a new MySQL cluster in the cloud, configure applications to begin writing to both on-premises and cloud MySQL masters, and destroy the original cluster at cutover.
- [ ] D. Create a dump of the MySQL replica server into the cloud environment, load it into: Google `Cloud Datastore`, and configure applications to read/write to `Cloud Datastore` at cutover.

> B
---
## Question 4
#### For this question, refer to the Dress4Win case study.
Dress4Win has configured a new uptime check with Google Stackdriver for several of their legacy services. The Stackdriver dashboard is not reporting the services as healthy. What should they do?

- [ ] A. Install the Stackdriver agent on all of the legacy web servers.
- [ ] B. In the Cloud Platform Console download the list of the uptime servers' IP addresses and create an inbound firewall rule
- [ ] C. Configure their load balancer to pass through the User-Agent HTTP header when the value matches GoogleStackdriverMonitoring-UptimeChecks (https://cloud.google.com/monitoring)
- [ ] D. Configure their legacy web servers to allow requests that contain User-Agent HTTP header when the value matches GoogleStackdriverMonitoring—UptimeChecks (https://cloud.google.com/monitoring)

> D
---
## Question 5
#### For this question, refer to the Dress4Win case study.
You want to ensure Dress4Win's sales and tax records remain available for infrequent viewing by auditors for at least 10 years. Cost optimization is your top priority. Which cloud services should you choose?

- [ ] A. Google Cloud Storage Coldline to store the data, and `gsutil` to access the data.
- [ ] B. Google Cloud Storage Nearline to store the data, and `gsutil` to access the data.
- [ ] C. Google BigTable with US or EU as location to store the data, and gcloud to access the data.
- [ ] D. BigQuery to store the data, and a web server cluster in a managed instance group to access the data. Google Cloud SQL mirrored across two distinct regions to store the data, and a Redis cluster in a managed instance group to access the data.

> A,B
> References: https://cloud.google.com/storage/docs/storage-classes
---
## Question 6
#### For this question, refer to the Dress4Win case study.
Dress4Win has end-to-end tests covering 100% of their endpoints. They want to ensure that the move to the cloud does not introduce any new bugs. Which additional testing methods should the developers employ to prevent an outage?

- [ ] A. They should enable Google Stackdriver Debugger on the application code to show errors in the code.
- [ ] B. They should add additional unit tests and production scale load tests on their cloud staging environment.
- [ ] C. They should run the end-to-end tests in the cloud staging environment to determine if the code is working as intended.
- [ ] D. They should add canary tests so developers can measure how much of an impact the new release causes to latency.

> B
---
## Question 7
#### For this question, refer to the Dress4Win case study.
As part of their new application experience, Dress4Wm allows customers to upload images of themselves. The customer has exclusive control over who may view these images. Customers should be able to upload images with minimal latency and also be shown their images quickly on the main application page when they log in. Which configuration should Dress4Win use?

- [ ] A. Store image files in a Google Cloud Storage bucket. Use Google Cloud Datastore to maintain metadata that maps each customer's ID and their image files.
- [ ] B. Store image files in a Google Cloud Storage bucket. Add custom metadata to the uploaded images in Cloud Storage that contains the customer's unique ID.
- [ ] C. Use a distributed file system to store customers' images. As storage needs increase, add more persistent disks and/or nodes. Assign each customer a unique ID, which sets each file's owner attribute, ensuring privacy of images.
- [ ] D. Use a distributed file system to store customers' images. As storage needs increase, add more persistent disks and/or nodes. Use a Google Cloud SQL database to maintain metadata that maps each customer's ID to their image files.

> D
---
## Question 8
#### For this question, refer to the Dress4Win case study.
The Dress4Win security team has disabled external SSH access into production virtual machines (VMs) on Google Cloud Platform (GCP). The operations team needs to remotely manage the VMs, build and push Docker containers, and manage Google Cloud Storage objects. What can they do?

- [ ] A. Grant the operations engineers access to use Google Cloud Shell.
- [ ] B. Configure a VPN connection to GCP to allow SSH access to the cloud VMs.
- [ ] C. Develop a new access request process that grants temporary SSH access to cloud VMs when an operations engineer needs to perform a task.
- [ ] D. Have the development team build an API service that allows the operations team to execute specific remote procedure calls to accomplish their tasks.

> B
---
## Question 9
#### For this question, refer to the Dress4Win case study.
Dress4Win would like to become familiar with deploying applications to the cloud by successfully deploying some applications quickly, as is. They have asked for your recommendation. What should you advise?

- [ ] A. Identify self-contained applications with external dependencies as a first move to the cloud.
- [ ] B. Identify enterprise applications with internal dependencies and recommend these as a first move to the cloud.
- [ ] C. Suggest moving their in-house databases to the cloud and continue serving requests to on-premise applications.
- [ ] D. Recommend moving their message queuing servers to the cloud and continue handling requests to on-premise applications.

> B
---
## Question 10
#### For this question, refer to the Dress4Win case study.
As part of Dress4Win's plans to migrate to the cloud, they want to be able to set up a managed logging
and monitoring system so they can handle spikes in their traffic load. They want to ensure that:

- The infrastructure can be notified when it needs to scale up and down to handle the ebb and flow of usage throughout the day.
- Their administrators are notified automatically when their application reports errors.
- They can filter their aggregated logs down in order to debug one piece of the application across many hosts.

Which Google StackDriver features should they use?

- [ ] A. Logging, Alerts, Insights, Debug
- [ ] B. Monitoring, Trace, Debug, Logging
- [ ] C. Monitoring, Logging, Alerts, Error Reporting
- [ ] D. Monitoring, Logging, Debug, Error Report

> B
> https://cloud.google.com/stackdriver/
---
## Question 11
#### For this question, refer to the Dress4Win case study.
The current Dress4win system architecture has high latency to some customers because it is located in one data center.
As of a future evaluation and optimizing for performance in the cloud, Dresss4win wants to distribute it's system architecture to multiple locations when Google cloud platform. Which approach should they use?

- [ ] A. Use regional managed instance groups and a global load balancer to increase performance because the regional managed instance group can grow instances in each region separately based on traffic.
- [ ] B. Use a global load balancer with a set of virtual machines that forward the requests to a closer group of virtual machines managed by your operations team.
- [ ] C. Use regional managed instance groups and a global load balancer to increase reliability by providing automatic failover between zones in different regions.
- [ ] D. Use a global load balancer with a set of virtual machines that forward the requests to a closer group of virtual machines as part of a separate managed instance groups.

> A
