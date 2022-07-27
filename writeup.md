# Operationalizing an AWS ML project 

## Providing the option to run notebooks locally
### Setting up a user in AWS with programmatic access
### Getting data
Only download/upload when required

## Using sagemaker 
### Select the right instance type for notebook
I decide to just go with the default instance type, namely ml.t3.medium. The notebook itself is doing very little, just coordinating the different tasks, such as initiating hyperparameter tuning, training and deployment. These activities themselves are happening on other instances. 

### Securing the notebook
Anyone who has access to the server can access the notebook TODO need to look at this more closely. In the spirit of securing the different resource I decided to experiment running the notebook inside a VPC. 
