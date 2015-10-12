Ansible Gogs
============

Install Gogs on EC2

Install Ansible
---------------
(On OSX for instance...)

    sudo easy_install pip
    sudo pip install --upgrade pip
    sudo -H pip install --upgrade boto
    sudo -H pip install --upgrade ansible


Configure your AWS Credentials
------------------------------

    export ANSIBLE_HOST_KEY_CHECKING=False
    export EC2_REGION=eu-west-1
    export AWS_ACCESS_KEY=...
    export AWS_SECRET_KEY=...
    export AWS_ACCESS_KEY_ID=$AWS_ACCESS_KEY
    export AWS_SECRET_ACCESS_KEY=$AWS_SECRET_KEY


Configure your EC2 pem file
---------------------------

    export PEM_NAME=<aws_pem_name>
    export PEM_PATH=~/.ssh/<aws_pem_name>.pem


Configure EC2 instances tags
----------------------------

    export CLIENT=company
    export ENV=dev


Configure your VPC
------------------

Use the default VPC or create one with a public subnet

    export VPC_ID=<vpc_id>
    export SUBNET_ID=<public_subnet_id>


Create EC2 instances
--------------------

    ansible-playbook -i inventory/local playbooks/create-ec2.yml


Configure EC2 instances
-----------------------

    ansible-playbook -i inventory/ec2.py playbooks/site.yml

    <or>

    ansible-playbook -i inventory/ec2.py playbooks/gogs.yml


You can browse
--------------

 `http://<gogs_host>:3000`
