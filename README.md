# ansible-ssh-distribute-key
* * *

## Description

Sets a user@host id_rsa.pub file as authorized on a set of other hosts.

By default it adds the inventory_hostname and short hostname to known hosts of the master host.

## Role dependencies

- _ssh-create-key_: ensures that user@master_host has a host key pair.

## Variables

Mandatory:
- _ssh_distribute_master_host_: master which distributes its public key.

Optional:
- _ssh_distribute_slave_host_user_: user to whose authorized_keys file is appended the public key to. Root if not specified. 
- _ssh_distribute_add_known_hosts_: <boolean>. Add host to known hosts (default True).
- _ssh_create_key_user_: user on master host whose key is retrieved from. Root if not specified. This variable is inherited from role ssh-create-key.
