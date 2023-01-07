## Deploy a high-availability web app using CloudFormation

### Scenario
Your company is creating an Instagram clone called Udagram.

Developers want to deploy a new application to the AWS infrastructure.

You have been tasked with provisioning the required infrastructure and deploying a dummy application, along with the necessary supporting software.

This needs to be automated so that the infrastructure can be discarded as soon as the testing team finishes their tests and gathers their results.

### Optional.
Add more challenge to the project, once the project is completed, you can try deploying sample website files located in a public S3 Bucket to the Apache Web Server running on an EC2 instance.

### Solution.

From the provided information, I have  a design an Architecture for Udagram using Lucid Chart as seen below. This architecture will be implementented in two categories i.e Network Infrastructure then Server Instances

To access the web app hosted click [here](http://udagr-webse-16d1geogl399k-898999464.us-east-1.elb.amazonaws.com/) 

![Udagram Architecture](UdagramArchitecture.jpeg)


### Creating the Network Stack
```
cd udacity-devops-engineer-project2
./create.sh udagram-Network networks.yml network-parameters.json aws-user-profile
```

### Updating the Network Stack
```
cd udacity-devops-engineer-project2
./update.sh udagram-Network networks.yml network-parameters.json aws-user-profile
```
## The server stack is cross-referencing values from the Network stack e.g VPCID
### Creating the Server Stack
```
cd udacity-devops-engineer-project2
./create.sh udagram-Servers servers.yml server-parameters.json aws-user-profile
```

### Updating the Server Stack
```
cd udacity-devops-engineer-project2
./update.sh udagram-Servers servers.yml server-parameters.json aws-user-profile
```