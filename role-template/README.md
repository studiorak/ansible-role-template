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

    in_dict_all_var: "{{ vars['in_dict_all_'+ cur_role_name] | default(omit)}}"
    in_dict_group_var: "{{ vars['in_dict_group_' + cur_role_name] | default(omit)}}"
    in_dict_host_var: "{{ vars['in_dict_host_' + cur_role_name] | default(omit)}}"
    in_dict_vault_var: "{{ vars['in_dict_vault_'+ cur_role_name] | default(omit)}}"

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
