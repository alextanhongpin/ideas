# Infrastructure as Code (IaC)

The following documentation will contain all the steps to recreate the whole environment + project in case of migration/failures.

Currently we have identified the following parts that needs to be automated:

- [x] Identity Server 4 Application (Dockerized at the moment)
- [ ] AWS Elastic Cache Redis (currently done through UI Console)
- [ ] AWS Elastic Container Service (currently done through UI Console)
- [ ] Database Migrations for MsSQL (Scripts to create the database and tables)
- [ ] Clients Registration (Scripts to create new Identity Server clients)

Part of the IaC is to also understand the resources required (storage size, instance size etc), network configuration (VPC settings, load balancers etc), and also the credentials (username, password, connection strings etc. that needs to be stored as environment variables).

End goal is to be able to confidently destroying and recreating a new instance in a matter of minutes.
