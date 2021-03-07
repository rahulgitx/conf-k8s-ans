## conf-k8s-ans
###  Configuration of a 3-node( 1 master and 2 worker) kubernetes cluster on AWS instances with the help of ansible.
This repository consist of 4 files and 2 folders excluding README.md file.
For quick configuration just download all of these files in your local folder and keep in mind the following steps:
* Make sure you have a ec2-user created in your vm/os. and copy all these files in /home/ec2-user/ if you don't want to get into much costumization.
* Add your AWS user key and ID by running ```export AWS_ACCESS_KEY_ID='AKIA**************'``` and ```export AWS_SECRET_ACCESS_KEY='6+SCCNzQ68OqfK**********************' ``` command on the current folder.
* Add the keys in <current_folder>/role/launching_instances/vars/main.yml file as well.
* Add the name of the key that you will be using in the instances in the same file as well. (Note: do not use any .pem or .ppk extension here)
* Make sure you have the .pem file of the key in your same folder where you'll the main.yml file.
* Add the name of your private key in the ansconf line 137.
* Run ```ansible-playbook main.yml```
