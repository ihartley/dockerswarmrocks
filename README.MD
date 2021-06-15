# dockerswarmrocks playbook 

Deploy a Docker Swarm cluster a la dockerswarm.rocks

## How to use


## Creating venv (optional but highly recommended)

The easiest way to ensure you have the right ansible and properly libs installed is to use a python venv. We're using poetry to manage this:

```
    cd ../../..
    poetry install && poetry shell
    cd ansible/playbooks/dockerswarmrocks
```

### Pre-reqs

1. `ansible-galaxy collection install -r roles/requirements.yml`
2. `ansible-galaxy install -r roles/requirements.yml -p roles`

### Running playbook locally

2. Run `ansible-playbook -c local -i inventory/inventory.ini dockerswarmrocks-playbook.yml`

### Running playbook on remote target server from local machine

1. Run `ansible-playbook -i inventory/<inventory_file> --key-file "~/.ssh/<private_key>" -u <user-remote> dockerswarmrocks-playbook.yml`

### Running playbook in dry mode (check)

1. Run `ansible-playbook -i inventory/<inventory_file> --key-file "~/.ssh/<private_key>" -u <user-remote> dockerswarmrocks-playbook.yml --diff --check`

### Provisioning with Vagrant

1. Download and install [VirtualBox](https://www.virtualbox.org/wiki/Downloads).
2. Download and install [Vagrant](http://www.vagrantup.com/downloads.html).
3. Create Virtual environment
4. Run `vagrant up` from `provisioner` folder to build the VM .
5. Run `vagrant destroy` from `provisioner` folder to delete the VM .

## License

BSD license

## Author

[Iain Hartley](mailto:iain@bitecompiler.com)

## Version

Release date: 2021-05-23
Version: 0.1.0