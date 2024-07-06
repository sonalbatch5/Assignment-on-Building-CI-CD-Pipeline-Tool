# cicd_project_steps
# Building CICD pipeline tool 

### This project provides a simple CI/CD pipeline tool implemented using Bash, Python, and crontabs. It automates the process of fetching code changes, building the application, running tests, and deploying the application.


### Step1: Clone the repository  https://github.com/sonalbatch5/cicd_project.git.
       This repository contains the following files:
       a) index.html: A simple html page.
       b) get_latest_commit.py: A python scrip to get the latest commit in the repo.
       c) master_script.py: A master script which will pull the latest changes from the repo and copy the changes into the nginx repo and restart the nginx service to deploy the html page.

### Step2: sudo apt get update: Update the host machine

### Step3: sudo apt install nginx: Install NGINX

### Step4: systemctl status nginx: Check the status of nginx service

### Step5:```* * * * * sudo /home/ubuntu/master_script.sh```: Create a cron stop to run the script at every 1 minute. sudo permissions will be needed to copy html file to nginx directory and restart the nginx service.

### Step6: Push a change to index.html.

### Step7: Open the address ```http://<hostmachine>/```: The web page should show the latest index.html page 

### Result: Cron job will run at every 1 min, which will run the master_script.sh script. This script will run the get_latest_commit.py. get_latest_commit.py will check for any latest commit in the repo and exit. The master_script.sh will pull the changes if any latest commit is done. The master_script.sh also copies the latest index.html in /var/www/html/ directory and restart the nginx service.
