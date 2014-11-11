Deploy
======

Prerequisite
------------
Must have these packages installed locally: 
sudo apt-get install ansible
sudo apt-get install git

Must have this project (deploy project) cloned and in CWD is that directory

If master node has not been configured before
---------------------------
ssh-keygen -q -t rsa -b 2048 -f ~/cluster -N ""
ssh-copy-id -i ~/cluster.pub manager@10.36.12.74
<input password>
rm cluster.pub
mv cluster cluster.pem

TEMPORARY: pushing locally
--------------------------
ansible-playbook -i hosts local_deploy.yml --connection=local

Pushing to Cluster
--------------
**MONGOLAB_URI environment variable must be set in your shell  To get the variable, log into Heroku and look at addons for metrics service.**
ansible-playbook -i hosts site.yml --private-key=./cluster.pem