## Quick Start Guide
1. Edit the hosts in the hosts.ini file as well as the authentication type. Swarm manager nodes should be placed under 'docker_swarm_manager' and swarm worker nodes should be placed under 'docker_swarm_mworker'.
2. Edit the 'swarm_iface' default variable in the docker role to match the primary iface used to communicate with nodes.
3. Check all hosts are accessible: ```ansible all -m ping -i production/hosts.ini```
4. Run the playbook: ```ansible-playbook -i production/hosts.ini site.yml```

## AWS Notes
1. Open protocols and ports between the hosts
The following ports must be available. On some systems, these ports are open by default.

- TCP port 2377 for cluster management communications
- TCP and UDP port 7946 for communication among nodes
- UDP port 4789 for overlay network traffic

## References: 
	- http://derpturkey.com/elasticsearch-cluster-with-docker-engine-swarm-mode/
	- https://github.com/nextrevision/ansible-swarm-playbook/blob/master/swarm.yml