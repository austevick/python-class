## PIP
+++
The python package manager is called pip. Pip handles several functions; namely installing, upgrading and removing packages
+++
Pip is often used within a virtualenv to separate the dependencies your project needs from python packages your operating system needs.
+++
To get started using pip in a project, you first need to create the project
```
mkdir project
cd project
virtualenv env
source env/bin/active
```
@[1](Create the folder that will contain our project)
@[2](cd into the new directory we created)
@[3](Create the virtualenv)
@[3](This will create a new directory called env)
@[4](Now we activate the virtualenv)
+++
Once the virtualenv is activated, we can start installing packages
```
pip install boto3
```
+++
We can now see that pip installed the boto3 package as well as all of boto3's dependencies by running `pip list --format columns`
```
(env) austin-laptop:project austin$ pip list --format columns
Package         Version
--------------- -------
boto3           1.5.35
botocore        1.8.49
docutils        0.14   
futures         3.2.0  
jmespath        0.9.3  
pip             9.0.1  
python-dateutil 2.6.1  
s3transfer      0.1.13
setuptools      38.5.1
six             1.11.0
wheel           0.30.0
```
+++
We can upgrade packages by running
```
pip install boto3 --upgrade
```
+++
Inversely, we can also remove packages by running:
```
pip uninstall boto3
```
+++
Many times when you are working with python projects, you will see a requirements.txt in the root of the project which contains a list of packages and the version you should be using.
+++
The requirements.txt file typically looks something like:
```
botocore==1.8.49
docutils==0.14
futures==3.2.0
jmespath==0.9.3
python-dateutil==2.6.1
s3transfer==0.1.13
six==1.11.0
```
+++
To install the packages listed in the requirements.txt file, you can run
```
pip install -r requirements.txt
```
where the -r flag is the path to the requirements.txt file. Since I am running this from the same directory the file is in, I just use `requirements.txt` and not something like `path/to/requirements.txt`
+++
When installing packages, you can either give pip the package name
```
pip install boto3
```
or a url to some sort of archive such as a zip file or tar file
```
pip install https://github.com/boto/boto3/archive/1.5.35.tar.gz
```
Lastly, you can also install directly from a git repository
```
pip install git+https://github.com/boto/boto3.git
```
