# Project Aster: Loading data into DynamoDB Global using Kinesis Data Stream and Lambda

An EC2 instances is used as a data producer using Kinesis agent.

## Description

This sample project to demonstratte the capability of data produced using Kineis agent running in an EC2 instance and loading the same to a DynamoDB global table using Lambda. An SQS is used a error destination. The DynamoDB global table, Kinesis Data Stream and SQS queue are all encrypted using Customer Managed KMS Keys

![Project Tauris - Design Diagram](https://subhamay-projects-repository-us-east-1.s3.amazonaws.com/0034-aster/aster-architecture-diagram.png)

## Getting Started

### Dependencies

* None

### Installing

* Clone the repository.
* Create a S3 bucket and make it public.
* Create the folders - 0034-aster/cft/nested-stacks/, 0034-aster/cft/cfn/, 0034-aster/code/python/, 0034-aster/code/log-generator/
* Upload the following YAML templates to 0034-aster/cft/nested-stacks/
    * ec2-instance-stack.yaml
    * dynamodb-stack.yaml
    * kinesis-data-stream-stack.yaml
    * sqs-stack.yaml
    * iam-role-stack.yaml
* Upload the following YAML templates to 0034-aster/cft/
    * aster-root-stack.yaml
* Remember to replace the bucket name in the YAML root stack with your public bucket.
* Zip and Upload the Python file aster.py to 0034-aster/code/python
* Upload the OnlineRetail.csv to the folder /0034-aster/code/log-generator/
* Upload the file log-generator.py and OnlineRetail.py to 0034-aster/code/log-generator/
* Create the entire using by using the root stack template 0034-aster/cft/cfn/aster-root-stack.yaml by providing the required parameters and the s3 cross stack name created in the previous step.

### Executing program

* Create the stack using the root stack template cfn-aster-root-stack.yaml
* SSH to the EC2 instance and run the log generator python script
* 
```
sudo ./LogGenerator.py <Any Random Number less than 50000>
```

## Help

Post message in my blog (https://blog.subhamay.com)


## Authors

Contributors names and contact info

Subhamay Bhattacharyya  - [subhamay.aws@gmail.com](https://blog.subhamay.com)

## Version History

* 0.1
    * Initial Release

## License

This project is licensed under Subhamay Bhattacharyya. All Rights Reserved.

## Acknowledgments

Inspiration, code snippets, etc.
* [Frank Kane ](https://www.linkedin.com/in/fkane/)

