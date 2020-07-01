# project-jam

This is a Notejam App project running in AWS.

PoC and solution validation steps.

1. Gathering and analyzing the application and customer's requirements.
2. Planning a new architecture.
3. Preparing a demo.
4. Preparations for a deployment.
5. A workshop for the customer.

## 1. Gathering and analyzing the application and customer's requirements.

Summary: HA, scalability, security, portability, automation,  separate environments for testing, code and deployments' pipelines.

## 2. Planning a new architecture.

A proposed new topology
![alt text](https://github.com/pjablonski123/project-jam/blob/master/arch-topology.jpg?raw=true)

## 3. Preparing a demo.

Demo available at http://node4it.com

A screenshot from the website:
![alt text](https://github.com/pjablonski123/project-jam/blob/master/test-notejam.jpg?raw=true)


Install Python package. 
yum install python-pip

```
[ec2-user@ip-172-31-20-161 django]$ sudo yum install python-pip
Loaded plugins: extras_suggestions, langpacks, priorities, update-motd
192 packages excluded due to repository priority protections
Resolving Dependencies
--> Running transaction check
---> Package python2-pip.noarch 0:9.0.3-1.amzn2.0.2 will be installed
--> Finished Dependency Resolution

Dependencies Resolved

=====================================================================================================================
 Package                    Arch                  Version                            Repository                 Size
=====================================================================================================================
Installing:
 python2-pip                noarch                9.0.3-1.amzn2.0.2                  amzn2-core                1.9 M

Transaction Summary
=====================================================================================================================
Install  1 Package

Total download size: 1.9 M
Installed size: 8.3 M
Is this ok [y/d/N]: y
Downloading packages:
python2-pip-9.0.3-1.amzn2.0.2.noarch.rpm                                                      | 1.9 MB  00:00:00     
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  Installing : python2-pip-9.0.3-1.amzn2.0.2.noarch                                                              1/1 
  Verifying  : python2-pip-9.0.3-1.amzn2.0.2.noarch                                                              1/1 

Installed:
  python2-pip.noarch 0:9.0.3-1.amzn2.0.2                                                                             

Complete!
```

pip install -r requirements.txt

```
[ec2-user@ip-172-31-20-161 django]$ sudo pip install -r requirements.txt
WARNING: Running pip install with root privileges is generally not a good idea. Try `pip install --user` instead.
Collecting Django==1.6.5 (from -r requirements.txt (line 1))
  Downloading https://files.pythonhosted.org/packages/43/6c/7fffbe73fe5703125aa1c9e3279ad3a5e542128ee55a4aa83669db1985cd/Django-1.6.5-py2.py3-none-any.whl (6.7MB)
    100% |████████████████████████████████| 6.7MB 174kB/s 
Collecting South==1.0 (from -r requirements.txt (line 2))
  Downloading https://files.pythonhosted.org/packages/43/05/1b910d9e3c9acda61f671c64c4b6ca79f495241602218ee6df95acd5616c/South-1.0.tar.gz (97kB)
    100% |████████████████████████████████| 102kB 9.5MB/s 
Installing collected packages: Django, South
  Running setup.py install for South ... done
Successfully installed Django-1.6.5 South-1.0
```

Run the service.
```
sudo ./manage.py runserver 172.31.20.161:80&
```

## 4. Preparations for a deployment.

1. Deployment of the old architecture in AWS using EC2 instances. 
2. A database migration from SQLite to an RDS instance.
3. Code patching and updates of the LAP stack, e.g. bump django from version 1.6.5 to 1.11.29.
4. Deploy network and other infrastructure components.
5. Performance and scalability verification, modify the architecture.
6. Create an AMI image based on an instance testing deployment.
7. Build CloudFormation templates for the whole infrastructure.
8. Deploy a full testing environment from the code.
9. Verify settings, stage period.
10. Prepare a docummentation.

## 5. A workshop for the customer.

Date of w workshop - TBD.
