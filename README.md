Ansible-role-metallb
=========

This role is made to apply config on Kubernetes cluster on a bare metal server

This role will setup dynamic IP for k8s loadbalancer

Requirements
------------

- Apply flannel CNI

Role Variables
--------------

Variable for available IP on the bare metal server 

````
metallb_start_range: 10.10.10.1
metallb_end_range: 10.10.10.20
kubernetes_master: True
````

Dependencies
------------

- role: ansible-role-crio_k8s

Example Playbook
----------------

- set a variable kubernetes_master on the master of your inventory

````
- hosts: master
roles:
  - 
    { role: ansible-role-crio_k8s }
  -
    { role: ansible-role-metallb, when: kubernetes_master }
````

License
-------

BSD

Author Information
------------------

gotoole
ops4cloud.fr
