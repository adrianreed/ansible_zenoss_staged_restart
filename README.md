# Zenoss Maintenance Staged Restart
Run a maintenance staged restart on a multi host Zenoss deployment

## Description
This playbook can be used to perform a maintenance staged restart on a multi host Zenoss deployment as described in the Zenoss support documentation:
https://support.zenoss.com/hc/en-us/articles/211783563-Zenoss-Master-Staged-Startup-and-Shutdown-Best-Practices-for-Maintenance-

Even though this playbook presumes a deployment consisting of a master node, a Zookeeper ensemble of worker nodes and a number of collector nodes, it should not take too much effort to tweak it a little and adjust it to other kinds of deployments.

## Usage
- Use the provided hosts.example file to build your '/etc/ansible/hosts' file.
- Copy the provided group_vars files to '/etc/ansible/hosts/group_vars/' and edit with the right parameters for your environment.
- Run the following commands to perform the procedure:
```
ansible-playbook main.yml --tags stop
ansible-playbook main.yml --tags clean
ansible-playbook main.yml --tags start
```
