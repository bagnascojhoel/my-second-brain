#overview #dictionary 
## Amazon Machine Image (AMI)
It is a specification to launch an EC2 instance. You can choose your AMI from some pre-defined specifications (which you can customize), can create your own with EC2 Image Builder, can buy one from AWS Marketplace or can pick one from the community.

![[Pasted image 20220223071141.png]]

## Systems Manager
### Parameter Store
Should be used to store and manage application parameters, such as database strings, license codes and any configuration that is not private enough to use Secrets Manager. Speaking of which, Secrets Manager secrets can be fetched with the Parameter Store API. 

![[Pasted image 20220223073230.png]]

## Secrets Manager
As the name says, it is used to store and manage secrets. It has some inate integrations to other AWS features. You can configure it to have a [schedule for automatic rotating for a secret](https://docs.aws.amazon.com/secretsmanager/latest/userguide/rotating-secrets.html). 

![[Pasted image 20220223072550.png]]

## AppSync
Create AWS managed GraphQL APIs. You define your data source, which can be a DynamoDB table, an OpenSearch domain, a Lambda function, a relational database or a HTTP endpoint. AWS will handle all infrastructure, scale on-demand, caching and client-side storage for offline devices.
