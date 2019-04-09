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
```
For this question, refer to the Dress4Win case study. At Dress4Win, an operations engineer wants to create a low-cost solution to remotely archive copies of database backup files. The database files are compressed tar files stored in their current data center. How should he proceed?
```

- [ ] A. Create a cron script using gsutil to copy the files to a Coldline Storage bucket.
- [ ] B. Create a cron script using gsutil to copy the files to a Regional Storage bucket.
- [ ] C. Create a Cloud Storage Transfer Service Job to copy the files to a Coldline Storage bucket.
- [x] **D. Create a Cloud Storage Transfer Service job to copy the files to a Regional Storage bucket.**

> Follow these rules of thumb when deciding whether to use gsutil or Storage Transfer Service:  
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
For this question, refer to the Dress4Win case study. Dress4Win has asked you to recommend machine types they should deploy their application servers to. How should you proceed?

- [ ] A. Perform a mapping of the on-premises physical hardware cores and RAM to the nearest machine types in the cloud.
- [ ] B. Recommend that Dress4Win deploy application servers to machine types that offer the highest RAM to CPU ratio available.
- [ ] C. Recommend that Dress4Win deploy into production with the smallest instances available, monitor them over time, and scale the machine type up until the desired performance is reached.
- [x] **D. Identify the number of virtual cores and RAM associated with the application server virtual machines align them to a custom machine type in the cloud, monitor performance and scale the machine types up until the desired performance is reached.**

---
## Question 3
For this question, refer to the Dress4Win case study.
Dress4Win has asked you for advice on how to migrate their on-premises MySQL deployment to the cloud. They want to minimize downtime and performance impact to their on-premises solution during the migration. Which approach should you recommend?

- [ ] A. Create a dump of the on-premises MySQL master server, and then shut it down, upload it to the cloud environment, and load into a new MySQL cluster.
- [x] **B. Setup a MySQL replica server/slave in the cloud environment, and configure it for asynchronous replication from the MySQL master server on-premises until cutover.**
- [ ] C. Create a new MySQL cluster in the cloud, configure applications to begin writing to both on-premises and cloud MySQL masters, and destroy the original cluster at cutover.
- [ ] D. Create a dump of the MySQL replica server into the cloud environment, load it into: Google `Cloud Datastore`, and configure applications to read/write to `Cloud Datastore` at cutover.