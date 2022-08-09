This setup suitable for Ubuntu 22.04 target servers.

Switch to kubeans:v1.24.3 sh shell with command below.

docker run -it phenomrascalov/kubeans:v1.24.3 sh

Generate ssh public key and private key with command below.

ssh-keygen

Share ssh public key to target master and worker servers with command below.

Example:

ssh-copy-id -i ~/.ssh/id_rsa.pub root@master01

ssh-copy-id -i ~/.ssh/id_rsa.pub root@worker01

Type the hostname of the master and worker servers into the inventory.yaml file.

Example inventory.yaml file

[master]
master01
[worker]
worker01

You can start the installation with the command below. 

ansible-playbook main.yaml -i inventory.yaml

