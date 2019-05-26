ansible-device-role
===================

Ansible role for operating a (fictional) Ansible FTL communications device

This role contains an Ansible module and an Action Plugin for operating the
Ansible device as well as a Lookup Plugin for iterating with a planet name
database.

This role had been written as part of a PyCon-IL 2019 'extending-ansible'
demonstrtion code.

Requirements
------------

- A working Ansible FTL communications device
- The `ansible_device` Python module installed on the Ansible device
- A database of planet names and aliases for use with the Ansible device
- The `planetdb` Python module installed on the Ansible (software) controller
  workstation.


Example Playbook
----------------

---
- hosts: ansible-device
  gather_facts: no
  roles:
    - ansible_device
  tasks:
    - name: Message to Dune
      ansible_message:
        destination: dune
        message: |
          Hi from Earth!

License
-------

GPL v3.0
