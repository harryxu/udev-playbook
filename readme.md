## Usage

### [Installing Ansible](https://docs.ansible.com/ansible/latest/installation_guide/installation_distros.html#installing-ansible-on-ubuntu)

```
sudo apt update
sudo apt install software-properties-common
sudo add-apt-repository --yes --update ppa:ansible/ansible
sudo apt install ansible
```

### Run Ansible commands inside this directory.

 * `ansible-galaxy install -r requirements.yml`
 * `ansible-playbook main.yml`
