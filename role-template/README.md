Role Name
=========

Template for role building 

# Several files are requested 
# !! IMPORTANT !! Please suit roles/role-cert-management/playbooks/00-deploy.yml to your role filename !!

{{ inventory_dir }}/group_vars
<br />├── all
<br />│   ├── all.yml      => variable dict : in_dict_all_role_my_role
<br />│   └── vault.yml    => all generic vaulted vars
<br />├── linux
<br />│   └── vault.yml    => variables : ansible_user, ansible_password
<br />└── windows
<br />    └── vault.yml    => variables : ansible_user, ansible_password, ansible_connection: winrm, ansible_winrm_transport: basic
<br /><br />
<br />{{ inventory_dir }}/host_vars
<br />├── host_vars
<br />    ├── my-first-server
<br />    │   └── vault.yml         => variables : ansible_user, ansible_password
<br />    └── my-second-server
<br />        └── vault.yml         => variables : ansible_user, ansible_password

Requirements
------------

None but basic usage of ansible

Role Variables
--------------

All these vars are overrided with below precedence :

var: in_dict_all_<my_role_name><br />
path: "{{ inventory_dir }}"/my_customer/group_vars/all/all.yml

var: in_dict_group_<my_role_name> 
path: "{{ inventory_dir }}"/my_customer/group_vars/<my_group>/<my_group>.yml

var: in_dict_host_<my_role_name> 
path: "{{ inventory_dir }}"/my_customer/host_vars/<my_hostname>/<my_hostname>.yml

var: in_dict_vault_<my_role_name> 
path: "{{ inventory_dir }}"/my_customer/group_vars/<my_group|my_hostname>/<my_group|my_hostname>.vault

Dependencies
------------

none

Example Playbook
----------------

included into the role : {{ role_path }}/playbooks/00-deploy.yml

License
-------

BSD

Author Information
------------------

I'm a poor lonesome cowboy !
