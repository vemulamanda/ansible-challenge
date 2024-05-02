Hi,
I was unable to completely automate it as i havent worked with ec2 modules. i have tried my best to do this.. 
I have also included docker example file which i had worked in my previous company. 
I have almost automated it, the only place manual intervention needed is during copying ssh keys to remote servers and updating the inventory hosts file. I tried to automate it but somehow it is not working.

(Note: Please run all commands from /etc/ansible folder)
1. Clone repo(dev branch) to /etc/ansible on ansible master.
2. Run "export ANSIBLE_VAULT_PASSWORD_FILE=/etc/ansible/vaultpassword.txt"
3. Run "ansible-lint site.yml"
4. Run "ansible-lint createserver.yml"
5. Run "ansible-galaxy collection install -r collections/requirements.yml"
6. Run "ansible-playbook -i inventory createserver.yml"
7. Manual Steps: Get the private ip address of two aws amazon linux servers and update inventory file(/etc/ansible/inventory/hosts) and create ssh connection to remote servers by creating keypair and copying ssh keys.
   Also rename the files under /etc/ansible/host_vars/ with names of your newly created servers private IP's. (I tried this but some error is stopping the script. you can find the code i tried in mislleneous-code.yml file)..
8. Run "ansible-playbook -i inventory site.yml"
9. THE SITE SHOULD BE UP NOW.. I haven't done http to https redirection..please type "https://your public ip".
