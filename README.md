Docker swarm 

---
this will setup docker swarm cluster 1 manager and two worker nodes
you have the execute the script in the following order
1) Vagrant File first
2) docker-cluster.yml - to setup the docker and other packages in master and worker nodes
3) swarmer.yml - this playbook will create the cluster with initial setup and manaagement

4) only manual things involved is to create the nodes inventory the ansible host machine

