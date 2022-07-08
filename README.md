# Hello Ansible

## run:

### local task
```sh
    sudo ansible-playbook main.yml
```

### remote task
```sh
    sudo ansible-playbook main-remote.yml -i inventory --private-key keyfile.pem
```