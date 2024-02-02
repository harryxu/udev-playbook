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


## Troubleshooting

### `ERROR: Ansible requires the locale encoding to be UTF-8; Detected None.`


```shell
$ export  LC_ALL=en_US.utf-8
```

### Python ImportError: cannot import name 'soft_unicode' from 'markupsafe'

If you see errors like below:

```
[WARNING]: Skipping plugin
(/home/vagrant/ansible/roles/nephelaiio.plugins/filter_plugins/custom_filters.py), cannot load:
cannot import name 'soft_unicode' from 'markupsafe' (/usr/lib/python3/dist-
packages/markupsafe/__init__.py)
fatal: [127.0.0.1]: FAILED! => {"msg": "template error while templating string: Could not load \"sorted_get\": 'sorted_get'. String: {{ nfs_packages_server | default(nfs_packages_server_default | sorted_get(overrides)) }}. Could not load \"sorted_get\": 'sorted_get'"}
```

[Downgrade python markupsafe package to 2.0.1](https://stackoverflow.com/a/72747002/157811)

```
pip install markupsafe==2.0.1
```
