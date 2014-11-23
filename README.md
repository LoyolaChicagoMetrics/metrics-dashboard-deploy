Deploy
======

Prerequisite
------------
Must have these packages installed locally (to get the latest version of ansible, older versions may not work): 

sudo apt-get install software-properties-common
sudo apt-add-repository ppa:ansible/ansible
sudo apt-get update
sudo apt-get install ansible
sudo apt-get install git

git clone https://github.com/mdotson/metrics-dashboard-deploy.git

Must have this project (deploy project) cloned and in CWD is that directory

Must have the environment variables GITHUB_USERNAME and GITHUB_PASSWORD set locally (used for API calls)

Pushing to Cluster
--------------
ansible-playbook -i hosts site.yml

Getting Predefined Ansible Facts for Nodes
------
ansible -i hosts -m setup backend_nodes --user ubuntu --sudo