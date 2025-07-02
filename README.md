Απαραίτητες προυποθέσεις:
1) Να έχει το vm το ssh κλειδί της συσκευής
2) Να υπάρχει το αρχείο .ssh/config με το group az-devops που να έχει μέσα το ip του μηχανήματος 135.225.132.230 και το ssh κλειδί του.
   
Βήματα εκτέλεσης:
(Για να κάνουμε εκτελέσουμε το spring-docker.yaml και τρέξει η εφαρμογή χρειάζεται να σταματήσουμε το spring.service, postgresql και mailhog για να τα απελευθερώσουμε!)

```
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
```

