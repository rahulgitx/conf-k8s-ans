## conf-k8s-ans
###  Configuration of a 3-node( 1 master and 2 worker) kubernetes cluster on AWS instances with the help of ansible.
This repository consist of 4 files and 2 folders excluding README.md file.
For **quick configuration** just download all of these files in your local folder and keep in mind the following steps:
* Make sure you have a ec2-user created in your vm/os. and copy all these files in /home/ec2-user/ if you don't want to get into much costumization.
* Add your AWS user key and ID by running ```export AWS_ACCESS_KEY_ID='AKIA**************'``` and ```export AWS_SECRET_ACCESS_KEY='6+SCCNzQ68OqfK**********************' ``` command on the current folder.
* Add the keys in <current_folder>/role/launching_instances/vars/main.yml file as well.
* Add the name of the key that you will be using in the instances in the same file as well. (Note: do not use any .pem or .ppk extension here)
* Make sure you have the .pem file of the key in your same folder where you'll the main.yml file.
* Add the name of your private key in the ansconf line 137.
* Run ```ansible-playbook main.yml```
* For more details follow [this article](www.medium "how to configure")

_Note: By default this role will launch three redhat free tier t2.micro instances in Mumbai region. Make changes in the role/launching_instances/vars/main.yml folder to customize according to you.


#### Inventory 
This file consists of two files that will help you create a dynamic inventory to automatically pick the new instances created. There is nothing that you need to change in these files.

#### role 
This is the one that contains all the ansible roles of **lauching the instances** , **configuring docker in the instances** , **making master node** and **making worker nodes**.

#### ansconf 
This folder needs to be there if you want to run the playbook with this dynamic inventory. The only change you have to make here is to add the .pem key.

#### conf 
This file is used to copy the content to configure bridge in kubernetes.

#### daemon.json
will change the cgroup driver to systemd in docker.

#### main.yml
Will run all the roles to configure the cluster.
