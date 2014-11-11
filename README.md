Deploy
======

Prerequisite
------------
Must have these packages installed locally: 
sudo apt-get install ansible
sudo apt-get install git
Must have cloned the git-commit-service and akka-cluster-example projects into the home directory.

If master node has not been configured before
---------------------------
ssh-keygen -q -t rsa -b 2048 -f ~/cluster.pub -N ""
ssh-copy-id -i ~/cluster.pub manager@10.36.12.74
<input password>
rm cluster.pub
mv cluster cluster.pem

Pushing to Cluster
--------------
**MONGOLAB_URI environment variable must be set in your shell  To get the variable, log into Heroku and look at addons for metrics service.**
ansible-playbook -i hosts site.yml --private-key=./cluster.pem