# Operationalizing an AWS ML project 

## Providing the option to run notebooks locally
### Setting up a user in AWS with programmatic access
### Getting data
I modified the notebook slightly so rather than just having commands that blindly download the data and then upload to S3 I've created a couple of functions that will check if the data has already been downloaded before downloading and check if it exists on S3 before uploading. This will avoid unneccessary downloads and uploads

I'm storing the data in the default sagemaker bucket as shown by the image below

s3-uploaded-files.png

As a side point, although I often prefer to run notebooks locally when transferring data to S3 this is quicker if done via a sagemaker hosted instance.


## Using sagemaker 
### Select the right instance type for notebook
I decide to just go with the default instance type, namely ml.t3.medium. The notebook itself is doing very little, just coordinating the different tasks, such as initiating hyperparameter tuning, training and deployment. These activities themselves are happening on other instances. 

sagemaker-notebook-instance.png

### Securing the notebook
Anyone who has access to the server can access the notebook TODO need to look at this more closely. In the spirit of securing the different resource I decided to experiment running the notebook inside a VPC. 

sagemaker-running-notebook-in-vpc.png

### Deployed endpoint
sagemaker-deployed-endpoint.png

endpoint name pytorch-inference-2022-07-27-18-49-58-516
