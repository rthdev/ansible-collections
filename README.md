# rthdev Ansible Collections

## Directory structure
    collection/
    ├── docs/
    ├── galaxy.yml
    ├── meta/
    │   └── runtime.yml
    ├── plugins/
    │   ├── modules/
    │   │   └── module1.py
    │   ├── inventory/
    │   └── .../
    ├── README.md
    ├── roles/
    │   ├── role1/
    │   ├── role2/
    │   └── .../
    ├── playbooks/
    │   ├── files/
    │   ├── vars/
    │   ├── templates/
    │   └── tasks/
    └── tests/
    
## How to configure and install
    $ cat ansible.cfg 
    [defaults]
    collections_paths = collections

    $ cat collections/requirements.yml 
    collections:
      - name: https://github.com/rthdev/ansible-collections.git
        type: git
        version: develop

    $ ansible-galaxy collection install -r collections/requirements.yml


## How to use
### Roles
    - role
      name: rthdev.general.<rolename>

### Playbooks
    - name: Use playbook from collection
      import_playbook: collections/ansible_collections/rthdev/general/playbooks/hello_world.yaml

