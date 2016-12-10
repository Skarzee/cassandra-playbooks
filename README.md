# playbooks
Ansible Playbooks

## Cassandra Snapshot (to) S3

To get a consistent snapshot of your Cassandra cluster it is necessary for you to run snapshots in parallel. With this being default behaviour within Ansible, it is a good option. Written with very little knowledge of Ansible, so suggestions, improvements and discussions are very welcome!

Please note you will have to define the variables required to use.

This playbook will take care of:

1. Generate a Dynamic Inventory to use with the specified tag 
2. Takes a snapshot via nodetool of all keyspaces, using the 'date' as a tag
3. Finds all directories within the specified data directory, this is then used for keyspace names
4. Within each of these directories, finds the directories with 'date'
5. With this snapshot location list, compress each
6. Finally, put them to S3

TO DO:
* How to restore easily via Ansible too?
* Sorage of variables elsewhere using Ansible-Vault
* Incremental Backups
* A play to clean up all folders with 'date' for later testing and improving


