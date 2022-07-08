# Hello Ansible

## Run:

### local task
```sh
    sudo ansible-playbook main.yml
```

### remote task
```sh
    sudo ansible-playbook main-remote.yml -i inventory --private-key keyfile.pem
```

## Resolve Error:

### 1. /usr/bin/python: not found
- set ansible playbook to use python3
```yml
 vars:
    ansible_python_interpreter: /usr/bin/python3
```

### 2. ImportError: cannot import name 'Mapping' from 'collections'
- install python 3.9
```sh
sudo apt update
sudo apt install software-properties-common
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt install python3.9
```
- In case if you face any dependency issue after installing Python 3.9
```sh
sudo apt-get -f install
```
- then set ansible playbook to use python3.9
```yml
 vars:
    ansible_python_interpreter: /usr/bin/python3.9
```

### 3. Could not import python modules: apt, apt_pkg:
- Go to python3 dist-package directory
```sh
cd /usr/lib/python3/dist-packages
```

- And then link these two files
```sh
sudo ln -s apt_inst.cpython-310-x86_64-linux-gnu.so apt_inst.so
sudo ln -s apt_pkg.cpython-310-x86_64-linux-gnu.so apt_pkg.so
```