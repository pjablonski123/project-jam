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


Install Python Package Manager. 
yum install python-pip

```
[ec2-user@ip-172-31-30-190 ~]$ yum install python-pip
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

yum install php -y
```
[ec2-user@ip-172-31-30-190 ~]$ yum install php -y
Loaded plugins: extras_suggestions, langpacks, priorities, update-motd
Resolving Dependencies
--> Running transaction check
---> Package php.x86_64 0:5.4.16-46.amzn2.0.2 will be installed
--> Processing Dependency: php-cli(x86-64) = 5.4.16-46.amzn2.0.2 for package: php-5.4.16-46.amzn2.0.2.x86_64
--> Processing Dependency: php-common(x86-64) = 5.4.16-46.amzn2.0.2 for package: php-5.4.16-46.amzn2.0.2.x86_64
--> Processing Dependency: httpd-mmn = 20120211x8664 for package: php-5.4.16-46.amzn2.0.2.x86_64
--> Processing Dependency: httpd for package: php-5.4.16-46.amzn2.0.2.x86_64
--> Running transaction check
---> Package httpd.x86_64 0:2.4.43-1.amzn2 will be installed
--> Processing Dependency: httpd-tools = 2.4.43-1.amzn2 for package: httpd-2.4.43-1.amzn2.x86_64
--> Processing Dependency: httpd-filesystem = 2.4.43-1.amzn2 for package: httpd-2.4.43-1.amzn2.x86_64
--> Processing Dependency: system-logos-httpd for package: httpd-2.4.43-1.amzn2.x86_64
--> Processing Dependency: mod_http2 for package: httpd-2.4.43-1.amzn2.x86_64
--> Processing Dependency: httpd-filesystem for package: httpd-2.4.43-1.amzn2.x86_64
--> Processing Dependency: /etc/mime.types for package: httpd-2.4.43-1.amzn2.x86_64
--> Processing Dependency: libaprutil-1.so.0()(64bit) for package: httpd-2.4.43-1.amzn2.x86_64
--> Processing Dependency: libapr-1.so.0()(64bit) for package: httpd-2.4.43-1.amzn2.x86_64
---> Package php-cli.x86_64 0:5.4.16-46.amzn2.0.2 will be installed
---> Package php-common.x86_64 0:5.4.16-46.amzn2.0.2 will be installed
--> Processing Dependency: libzip.so.2()(64bit) for package: php-common-5.4.16-46.amzn2.0.2.x86_64
--> Running transaction check
---> Package apr.x86_64 0:1.6.3-5.amzn2.0.2 will be installed
---> Package apr-util.x86_64 0:1.6.1-5.amzn2.0.2 will be installed
--> Processing Dependency: apr-util-bdb(x86-64) = 1.6.1-5.amzn2.0.2 for package: apr-util-1.6.1-5.amzn2.0.2.x86_64
---> Package generic-logos-httpd.noarch 0:18.0.0-4.amzn2 will be installed
---> Package httpd-filesystem.noarch 0:2.4.43-1.amzn2 will be installed
---> Package httpd-tools.x86_64 0:2.4.43-1.amzn2 will be installed
---> Package libzip010-compat.x86_64 0:0.10.1-9.amzn2.0.5 will be installed
---> Package mailcap.noarch 0:2.1.41-2.amzn2 will be installed
---> Package mod_http2.x86_64 0:1.15.3-2.amzn2 will be installed
--> Running transaction check
---> Package apr-util-bdb.x86_64 0:1.6.1-5.amzn2.0.2 will be installed
--> Finished Dependency Resolution

Dependencies Resolved

==========================================================================================================
 Package                       Arch             Version                        Repository            Size
==========================================================================================================
Installing:
 php                           x86_64           5.4.16-46.amzn2.0.2            amzn2-core           1.4 M
Installing for dependencies:
 apr                           x86_64           1.6.3-5.amzn2.0.2              amzn2-core           118 k
 apr-util                      x86_64           1.6.1-5.amzn2.0.2              amzn2-core            99 k
 apr-util-bdb                  x86_64           1.6.1-5.amzn2.0.2              amzn2-core            19 k
 generic-logos-httpd           noarch           18.0.0-4.amzn2                 amzn2-core            19 k
 httpd                         x86_64           2.4.43-1.amzn2                 amzn2-core           1.3 M
 httpd-filesystem              noarch           2.4.43-1.amzn2                 amzn2-core            23 k
 httpd-tools                   x86_64           2.4.43-1.amzn2                 amzn2-core            87 k
 libzip010-compat              x86_64           0.10.1-9.amzn2.0.5             amzn2-core            30 k
 mailcap                       noarch           2.1.41-2.amzn2                 amzn2-core            31 k
 mod_http2                     x86_64           1.15.3-2.amzn2                 amzn2-core           146 k
 php-cli                       x86_64           5.4.16-46.amzn2.0.2            amzn2-core           2.8 M
 php-common                    x86_64           5.4.16-46.amzn2.0.2            amzn2-core           563 k

Transaction Summary
==========================================================================================================
Install  1 Package (+12 Dependent packages)

Total download size: 6.6 M
Installed size: 22 M
Downloading packages:
(1/13): apr-1.6.3-5.amzn2.0.2.x86_64.rpm                                           | 118 kB  00:00:00     
(2/13): apr-util-1.6.1-5.amzn2.0.2.x86_64.rpm                                      |  99 kB  00:00:00     
(3/13): apr-util-bdb-1.6.1-5.amzn2.0.2.x86_64.rpm                                  |  19 kB  00:00:00     
(4/13): generic-logos-httpd-18.0.0-4.amzn2.noarch.rpm                              |  19 kB  00:00:00     
(5/13): httpd-filesystem-2.4.43-1.amzn2.noarch.rpm                                 |  23 kB  00:00:00     
(6/13): httpd-2.4.43-1.amzn2.x86_64.rpm                                            | 1.3 MB  00:00:00     
(7/13): httpd-tools-2.4.43-1.amzn2.x86_64.rpm                                      |  87 kB  00:00:00     
(8/13): mailcap-2.1.41-2.amzn2.noarch.rpm                                          |  31 kB  00:00:00     
(9/13): mod_http2-1.15.3-2.amzn2.x86_64.rpm                                        | 146 kB  00:00:00     
(10/13): libzip010-compat-0.10.1-9.amzn2.0.5.x86_64.rpm                            |  30 kB  00:00:00     
(11/13): php-5.4.16-46.amzn2.0.2.x86_64.rpm                                        | 1.4 MB  00:00:00     
(12/13): php-common-5.4.16-46.amzn2.0.2.x86_64.rpm                                 | 563 kB  00:00:00     
(13/13): php-cli-5.4.16-46.amzn2.0.2.x86_64.rpm                                    | 2.8 MB  00:00:00     
----------------------------------------------------------------------------------------------------------
Total                                                                      23 MB/s | 6.6 MB  00:00:00     
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  Installing : apr-1.6.3-5.amzn2.0.2.x86_64                                                          1/13 
  Installing : apr-util-bdb-1.6.1-5.amzn2.0.2.x86_64                                                 2/13 
  Installing : apr-util-1.6.1-5.amzn2.0.2.x86_64                                                     3/13 
  Installing : httpd-tools-2.4.43-1.amzn2.x86_64                                                     4/13 
  Installing : generic-logos-httpd-18.0.0-4.amzn2.noarch                                             5/13 
  Installing : mailcap-2.1.41-2.amzn2.noarch                                                         6/13 
  Installing : libzip010-compat-0.10.1-9.amzn2.0.5.x86_64                                            7/13 
  Installing : php-common-5.4.16-46.amzn2.0.2.x86_64                                                 8/13 
  Installing : php-cli-5.4.16-46.amzn2.0.2.x86_64                                                    9/13 
  Installing : httpd-filesystem-2.4.43-1.amzn2.noarch                                               10/13 
  Installing : mod_http2-1.15.3-2.amzn2.x86_64                                                      11/13 
  Installing : httpd-2.4.43-1.amzn2.x86_64                                                          12/13 
  Installing : php-5.4.16-46.amzn2.0.2.x86_64                                                       13/13 
  Verifying  : apr-util-1.6.1-5.amzn2.0.2.x86_64                                                     1/13 
  Verifying  : httpd-filesystem-2.4.43-1.amzn2.noarch                                                2/13 
  Verifying  : apr-util-bdb-1.6.1-5.amzn2.0.2.x86_64                                                 3/13 
  Verifying  : php-cli-5.4.16-46.amzn2.0.2.x86_64                                                    4/13 
  Verifying  : httpd-2.4.43-1.amzn2.x86_64                                                           5/13 
  Verifying  : mod_http2-1.15.3-2.amzn2.x86_64                                                       6/13 
  Verifying  : php-5.4.16-46.amzn2.0.2.x86_64                                                        7/13 
  Verifying  : libzip010-compat-0.10.1-9.amzn2.0.5.x86_64                                            8/13 
  Verifying  : apr-1.6.3-5.amzn2.0.2.x86_64                                                          9/13 
  Verifying  : mailcap-2.1.41-2.amzn2.noarch                                                        10/13 
  Verifying  : generic-logos-httpd-18.0.0-4.amzn2.noarch                                            11/13 
  Verifying  : php-common-5.4.16-46.amzn2.0.2.x86_64                                                12/13 
  Verifying  : httpd-tools-2.4.43-1.amzn2.x86_64                                                    13/13 

Installed:
  php.x86_64 0:5.4.16-46.amzn2.0.2                                                                        

Dependency Installed:
  apr.x86_64 0:1.6.3-5.amzn2.0.2                    apr-util.x86_64 0:1.6.1-5.amzn2.0.2                   
  apr-util-bdb.x86_64 0:1.6.1-5.amzn2.0.2           generic-logos-httpd.noarch 0:18.0.0-4.amzn2           
  httpd.x86_64 0:2.4.43-1.amzn2                     httpd-filesystem.noarch 0:2.4.43-1.amzn2              
  httpd-tools.x86_64 0:2.4.43-1.amzn2               libzip010-compat.x86_64 0:0.10.1-9.amzn2.0.5          
  mailcap.noarch 0:2.1.41-2.amzn2                   mod_http2.x86_64 0:1.15.3-2.amzn2                     
  php-cli.x86_64 0:5.4.16-46.amzn2.0.2              php-common.x86_64 0:5.4.16-46.amzn2.0.2               

Complete!
```

yum install git -y
```
[ec2-user@ip-172-31-30-190 ~]$ yum install git -y
Loaded plugins: extras_suggestions, langpacks, priorities, update-motd
Resolving Dependencies
--> Running transaction check
---> Package git.x86_64 0:2.23.3-1.amzn2.0.1 will be installed
--> Processing Dependency: perl-Git = 2.23.3-1.amzn2.0.1 for package: git-2.23.3-1.amzn2.0.1.x86_64
--> Processing Dependency: git-core-doc = 2.23.3-1.amzn2.0.1 for package: git-2.23.3-1.amzn2.0.1.x86_64
--> Processing Dependency: git-core = 2.23.3-1.amzn2.0.1 for package: git-2.23.3-1.amzn2.0.1.x86_64
--> Processing Dependency: emacs-filesystem >= 25.3 for package: git-2.23.3-1.amzn2.0.1.x86_64
--> Processing Dependency: perl(Term::ReadKey) for package: git-2.23.3-1.amzn2.0.1.x86_64
--> Processing Dependency: perl(Git::I18N) for package: git-2.23.3-1.amzn2.0.1.x86_64
--> Processing Dependency: perl(Git) for package: git-2.23.3-1.amzn2.0.1.x86_64
--> Processing Dependency: libsecret-1.so.0()(64bit) for package: git-2.23.3-1.amzn2.0.1.x86_64
--> Running transaction check
---> Package emacs-filesystem.noarch 1:25.3-3.amzn2.0.1 will be installed
---> Package git-core.x86_64 0:2.23.3-1.amzn2.0.1 will be installed
---> Package git-core-doc.noarch 0:2.23.3-1.amzn2.0.1 will be installed
---> Package libsecret.x86_64 0:0.18.5-2.amzn2.0.2 will be installed
---> Package perl-Git.noarch 0:2.23.3-1.amzn2.0.1 will be installed
--> Processing Dependency: perl(Error) for package: perl-Git-2.23.3-1.amzn2.0.1.noarch
---> Package perl-TermReadKey.x86_64 0:2.30-20.amzn2.0.2 will be installed
--> Running transaction check
---> Package perl-Error.noarch 1:0.17020-2.amzn2 will be installed
--> Finished Dependency Resolution

Dependencies Resolved

==========================================================================================================
 Package                     Arch              Version                        Repository             Size
==========================================================================================================
Installing:
 git                         x86_64            2.23.3-1.amzn2.0.1             amzn2-core            135 k
Installing for dependencies:
 emacs-filesystem            noarch            1:25.3-3.amzn2.0.1             amzn2-core             64 k
 git-core                    x86_64            2.23.3-1.amzn2.0.1             amzn2-core            5.0 M
 git-core-doc                noarch            2.23.3-1.amzn2.0.1             amzn2-core            2.4 M
 libsecret                   x86_64            0.18.5-2.amzn2.0.2             amzn2-core            153 k
 perl-Error                  noarch            1:0.17020-2.amzn2              amzn2-core             32 k
 perl-Git                    noarch            2.23.3-1.amzn2.0.1             amzn2-core             47 k
 perl-TermReadKey            x86_64            2.30-20.amzn2.0.2              amzn2-core             31 k

Transaction Summary
==========================================================================================================
Install  1 Package (+7 Dependent packages)

Total download size: 7.9 M
Installed size: 41 M
Downloading packages:
(1/8): git-2.23.3-1.amzn2.0.1.x86_64.rpm                                           | 135 kB  00:00:00     
(2/8): emacs-filesystem-25.3-3.amzn2.0.1.noarch.rpm                                |  64 kB  00:00:00     
(3/8): git-core-doc-2.23.3-1.amzn2.0.1.noarch.rpm                                  | 2.4 MB  00:00:00     
(4/8): git-core-2.23.3-1.amzn2.0.1.x86_64.rpm                                      | 5.0 MB  00:00:00     
(5/8): libsecret-0.18.5-2.amzn2.0.2.x86_64.rpm                                     | 153 kB  00:00:00     
(6/8): perl-Error-0.17020-2.amzn2.noarch.rpm                                       |  32 kB  00:00:00     
(7/8): perl-Git-2.23.3-1.amzn2.0.1.noarch.rpm                                      |  47 kB  00:00:00     
(8/8): perl-TermReadKey-2.30-20.amzn2.0.2.x86_64.rpm                               |  31 kB  00:00:00     
----------------------------------------------------------------------------------------------------------
Total                                                                      32 MB/s | 7.9 MB  00:00:00     
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  Installing : git-core-2.23.3-1.amzn2.0.1.x86_64                                                     1/8 
  Installing : git-core-doc-2.23.3-1.amzn2.0.1.noarch                                                 2/8 
  Installing : 1:perl-Error-0.17020-2.amzn2.noarch                                                    3/8 
  Installing : perl-TermReadKey-2.30-20.amzn2.0.2.x86_64                                              4/8 
  Installing : libsecret-0.18.5-2.amzn2.0.2.x86_64                                                    5/8 
  Installing : 1:emacs-filesystem-25.3-3.amzn2.0.1.noarch                                             6/8 
  Installing : perl-Git-2.23.3-1.amzn2.0.1.noarch                                                     7/8 
  Installing : git-2.23.3-1.amzn2.0.1.x86_64                                                          8/8 
  Verifying  : 1:emacs-filesystem-25.3-3.amzn2.0.1.noarch                                             1/8 
  Verifying  : git-2.23.3-1.amzn2.0.1.x86_64                                                          2/8 
  Verifying  : libsecret-0.18.5-2.amzn2.0.2.x86_64                                                    3/8 
  Verifying  : perl-TermReadKey-2.30-20.amzn2.0.2.x86_64                                              4/8 
  Verifying  : git-core-2.23.3-1.amzn2.0.1.x86_64                                                     5/8 
  Verifying  : 1:perl-Error-0.17020-2.amzn2.noarch                                                    6/8 
  Verifying  : perl-Git-2.23.3-1.amzn2.0.1.noarch                                                     7/8 
  Verifying  : git-core-doc-2.23.3-1.amzn2.0.1.noarch                                                 8/8 

Installed:
  git.x86_64 0:2.23.3-1.amzn2.0.1                                                                         

Dependency Installed:
  emacs-filesystem.noarch 1:25.3-3.amzn2.0.1             git-core.x86_64 0:2.23.3-1.amzn2.0.1            
  git-core-doc.noarch 0:2.23.3-1.amzn2.0.1               libsecret.x86_64 0:0.18.5-2.amzn2.0.2           
  perl-Error.noarch 1:0.17020-2.amzn2                    perl-Git.noarch 0:2.23.3-1.amzn2.0.1            
  perl-TermReadKey.x86_64 0:2.30-20.amzn2.0.2           

Complete!
```
git clone https://github.com/pjablonski123/project-jam.git /var/www/html
```
[ec2-user@ip-172-31-30-190 ~]$ git clone https://github.com/pjablonski123/project-jam.git /var/www/html
Cloning into '/var/www/html'...
remote: Enumerating objects: 125, done.
remote: Counting objects: 100% (125/125), done.
remote: Compressing objects: 100% (102/102), done.
remote: Total 125 (delta 42), reused 69 (delta 16), pack-reused 0
Receiving objects: 100% (125/125), 1.96 MiB | 3.81 MiB/s, done.
Resolving deltas: 100% (42/42), done.
```
pip install -r /var/www/html/django/requirements.txt
```
[ec2-user@ip-172-31-30-190 ~]$ pip install -r /var/www/html/django/requirements.txt
Collecting Django==1.11.29 (from -r /var/www/html/django/requirements.txt (line 1))
  Downloading https://files.pythonhosted.org/packages/49/49/178daa8725d29c475216259eb19e90b2aa0b8c0431af8c7e9b490ae6481d/Django-1.11.29-py2.py3-none-any.whl (6.9MB)
    100% |████████████████████████████████| 7.0MB 168kB/s 
Collecting South==1.0 (from -r /var/www/html/django/requirements.txt (line 2))
  Downloading https://files.pythonhosted.org/packages/43/05/1b910d9e3c9acda61f671c64c4b6ca79f495241602218ee6df95acd5616c/South-1.0.tar.gz (97kB)
    100% |████████████████████████████████| 102kB 9.7MB/s 
Collecting pytz (from Django==1.11.29->-r /var/www/html/django/requirements.txt (line 1))
  Downloading https://files.pythonhosted.org/packages/4f/a4/879454d49688e2fad93e59d7d4efda580b783c745fd2ec2a3adf87b0808d/pytz-2020.1-py2.py3-none-any.whl (510kB)
    100% |████████████████████████████████| 512kB 2.4MB/s 
Installing collected packages: pytz, Django, South
  Running setup.py install for South ... done
Successfully installed Django-1.11.29 South-1.0 pytz-2020.1
```

A modification of requirements.txt to Django 1.6.9.
```
[ec2-user@ip-172-31-30-190 ~]$ pip install -r /var/www/html/django/requirements.txt
WARNING: Running pip install with root privileges is generally not a good idea. Try `pip install --user` instead.
Collecting Django==1.6.9 (from -r /var/www/html/django/requirements.txt (line 1))
  Downloading https://files.pythonhosted.org/packages/c7/cb/1b2eb81a62f81e862c90675915dd07375d459d789ef372198abec9fbdc7a/Django-1.6.9-py2.py3-none-any.whl (6.7MB)
    100% |████████████████████████████████| 6.7MB 183kB/s 
Collecting South==1.0 (from -r /var/www/html/django/requirements.txt (line 2))
  Using cached https://files.pythonhosted.org/packages/43/05/1b910d9e3c9acda61f671c64c4b6ca79f495241602218ee6df95acd5616c/South-1.0.tar.gz
Installing collected packages: Django, South
  Found existing installation: Django 1.11.29
    Uninstalling Django-1.11.29:
      Successfully uninstalled Django-1.11.29
  Running setup.py install for South ... done
Successfully installed Django-1.6.9 South-1.0
```
./manage.py syncdb
```
[ec2-user@ip-172-31-30-190 ~]$ /var/www/html/django/notejam/manage.py syncdb
Syncing...
Creating tables ...
Creating table auth_permission
Creating table auth_group_permissions
Creating table auth_group
Creating table auth_user_groups
Creating table auth_user_user_permissions
Creating table auth_user
Creating table django_content_type
Creating table django_session
Creating table django_site
Creating table south_migrationhistory

You just installed Django's auth system, which means you don't have any superusers defined.
Would you like to create one now? (yes/no): yes
Username (leave blank to use 'root'): user
Email address: user@user.com
Password: 
Password (again): 
Superuser created successfully.
Installing custom SQL ...
Installing indexes ...
Installed 0 object(s) from 0 fixture(s)

Synced:
 > django.contrib.auth
 > django.contrib.contenttypes
 > django.contrib.sessions
 > django.contrib.sites
 > django.contrib.messages
 > django.contrib.staticfiles
 > users
 > south

Not synced (use migrations):
 - pads
 - notes
(use ./manage.py migrate to migrate these)
```
./manage.py migrate
```
[ec2-user@ip-172-31-30-190 ~]$ /var/www/html/django/notejam/manage.py migrate
Running migrations for pads:
 - Migrating forwards to 0001_initial.
 > pads:0001_initial
 - Loading initial data for pads.
Installed 0 object(s) from 0 fixture(s)
Running migrations for notes:
 - Migrating forwards to 0001_initial.
 > notes:0001_initial
 - Loading initial data for notes.
Installed 0 object(s) from 0 fixture(s)
```

Run the service.
```
/var/www/html/django/notejam/manage.py runserver 172.31.30.190:80
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
