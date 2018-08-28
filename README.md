#This is my first project for DocuTAP
#This commit is to test for githooks
#The below information is a guide
################### This is a brief guide ######################
THIS GUIDE WILL WORK YOU THROUGH DEPLOYING THE CICD PROJECT FOR DOCUTAP
Assumptions: This guide will assume that you already know the following:
How to use:
  •	GitHub
  •	Jenkins
  •	EC2
  •	AWS S3
  •	Chef
  •	Python
This guide will cover the following:
  1.	All the tools and environments that was used to implement this project
  2.	All the tools used on this project and what each tool will do in the CICD Project 
  3.	The necessary configuration  files and account information that you will need to contribute or deploy the project

ALL THE TOOLS THAT WAS USED TO IMPLEMENT THIS PROJECT
  1.	GitHub for our SCM
  2.	Jenkins for our Automation Engine/CI Server
  3.	4 AWS EC2 SERVERS
  4.	AWS S3
  5.	Chef for our CMS
  6.	Python

WHAT EACH TOOL WILL DO FOR THIS PROJECT
1. GIT HUB: The GitHub repo will hold all the necessary codes/scripts that was used throughout this project. The codes will be
	.The Python script
	.Bash script
	.Recipes and Cookbooks

2. JENKINS: The Jenkins CI server has been set up to integrate with the GitHub repo for the purpose of checking for changes in the repo.    The Jenkins server has a master slave relationship where the Jenkins Master is soley use for running the GUI while the Slave is used    solely for building jobs. For every new changes to the repo there are to jobs/projects that will automatically kick-off;
  .Job #1 (DocuTAP-Project1): Will list out the changes on the GitHub repo showing the new commit and kick off job  another job (job #2)    as a downstream project
  .Job #2 (python-script-for-listing-an-s3-bucket): Will ryn a simple python script that will list out    the content of an S3 bucket

3. 4 AWS EC2 SERVERS/INSTANCES: The 4 EC2 Servers for this project runs the below applications
  1.	Jenkins Master (GUI dashboard for kicking off jobs)
  2.	Jenkins Slave (For running the jobs)
  3.	Chef Master/Control Server (GUI Dashboard)
  4.	Chef WorkStation (For writing cookbooks and recipes used to check the state of the node(s) that the Chef Master is monitoring)

4. AWS S3: Used for storing different random objects/keys

5. CHEF MASTER AND SLAVE WORK STATION: The Chef Master hold the Chef GUI that is used to visually see the different node(s) that it checks with and also used for doing administrative task. 

The Chef WorkStation is used for pulling the current state of the different nodes and pushing out different cookbooks and recipes for administrative tasks. This Chef Master is currently monitoring one single node which is the Jenkins Slave.

6. PYHTHON: Python will be used as the script of choice to list out the object/keys of an S3 bucket
