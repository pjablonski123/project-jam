# project-jam

This is a Notejam App project running in AWS.

PoC and a solution validation steps.

1. Gathering and analyzing the application and customer's requirements.
2. Planning a new architecture.
3. Preparing a demo and a deployment.
4. A workshop for the customer.

## Gathering and analyzing the application and customer's requirements.

Summary: HA, scalability, security, portability, automation,  separate environments for testing, code and deployments' pipelines.

## Planning a new architecture.

A proposed new topology
![alt text](https://github.com/pjablonski123/project-jam/blob/master/arch-topology.jpg?raw=true)

## Preparing a demo and a deployment.

Demo available at http://node4it.com

A screenshot from the website:
![alt text](https://github.com/pjablonski123/project-jam/blob/master/test-notejam.jpg?raw=true)

Preparations for a deployment.

1. Deployment of the old architecture in AWS using EC2 instances. 
2. A database migration from SQLite to an RDS instance.
3. Code patching and updates of the LAP stack, e.g. bump django from version 1.6.5 to 1.11.29.
4. Performance and scalability verification, modify the architecture.
5. Build CloudFormation templates.
6. Deploy a full testing environment from the code.
7. Verify settings, stage period.
8. Prepare a docummentation.

## A workshop for the customer.

