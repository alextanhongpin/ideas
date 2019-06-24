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



## Strategy

### IAC

Infrastructure as Code can be done using several tools:
- AWS CLI
- EB Cli (Only for ElasticBeanstalk, since the AWS CLI does not have an option to deploy the changes to AWS)
- Terraform (preferred, only if the complexity is worth it)

### CI/CD

First Stage
- Manual build steps. Images has to be dockerised, tested, pushed to the private registry and applications has to be updated in production.

Second Stage
- Every commit will execute the tests, and once the test passes, it should deployed to Staging directly
- Deployment to production can be done by creating tags

### Deployments
- Applications are dockerized and deployed to AWS 
- Options are ElasticBeanstalk, ECS, EC2…

## Tagging Strategies

[Amazon](https://aws.amazon.com/answers/account-management/aws-tagging-strategies/) has a good summary on tagging strategies. It's important to have a well-defined tags not just to make it easier to identify the costs, but also better visibility on the roles of each resources. It's also important to know who/when deployed the applications and when it needs to be brought down. How the applications are deployed (IAC url) etc can also be added to tags to *inform* future developers on how the applications are deployed and what they need to consider before making changes etc).


## Planning Large Terraform Projects

- how to setup workflow for different environment (production, staging, etc)
- how to test the setup?
- how to manage chain workflows (creation of one resource requires details from another resources) without coupling them


## Versioning Application

How to measure performance changes when versioning application? Every release (new features) will definitely slow down the application. How to detect the threshold that is allowed? Possibly through prometheus, find a way to inject the version of the application, then plot the graph through grafana.

## Chaos Monkey Testing

The idea of terminating instance is not difficult. But integrating resiliency to services is the main idea behind chaos monkey testing. Are there better ways to integrate it? Here are some things that can be considered when writing services:

- what happens when the database is down?
- what happens when a service call fails (retries, circuit breaker)?
- what happens when the infra fails (cache, config)?
- what happens when the wrong configuration is passed in?
- what happens when the database is empty?
- how to plot the graph of relationship between services?
