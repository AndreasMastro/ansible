***
myubuntu@DESKTOP-CV4CP4M:~/ansible-devops-2025/ansible/ansible-devops-2025$ ansible-playbook playbooks/spring.yaml -l devops-vm-1
myubuntu@DESKTOP-CV4CP4M:~/ansible-devops-2025/ansible/ansible-devops-2025$ ssh az-devops 
azureuser@devops-vm-1:~$ sudo systemctl stop spring
azureuser@devops-vm-1:~$ sudo systemctl stop spring.service
azureuser@devops-vm-1:~$ sudo systemctl stop postgresql
azureuser@devops-vm-1:~$ sudo systemctl stop mailhog
azureuser@devops-vm-1:~$ exit
myubuntu@DESKTOP-CV4CP4M:~/ansible-devops-2025/ansible/ansible-devops-2025$ ansible-playbook playbooks/springdocker.yaml -l devops-vm-1
myubuntu@DESKTOP-CV4CP4M:~/ansible-devops-2025/ansible/ansible-devops-2025$ ssh az-devops 
azureuser@devops-vm-1:~$ cd spring/
azureuser@devops-vm-1:~/spring$ cd rentestatefinal-master/
azureuser@devops-vm-1:~/spring/rentestatefinal-master$ docker compose down
***
