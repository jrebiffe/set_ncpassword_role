Set Transmitted Power Level Role
================================

As a demonstration of NETCONF for Microwave, this Ansible role
change the description of ETH-14-255-2, to mimic a password change.
**Not intented to provide real usage.**

Role Variables
--------------

This demonstrator use only 1 settable variables: `password`.

| Parameter          | Type   | Required | Example         | Comments                                                         |
|--------------------|--------|----------|-----------------|------------------------------------------------------------------|
| `ncpwd_password`   | str    | Yes      | NotSoSecure123* | Set the user password. Example: "NotSoSecure123*".               |

Dependencies
------------

The [`ansible.netcommon`](https://galaxy.ansible.com/ui/repo/published/ansible/netcommon/)
collection is required, because the module
[`netconf_config`](https://docs.ansible.com/ansible/latest/collections/ansible/netcommon/netconf_config_module.html)
is used.

Example Playbook
----------------

Here is a fully functional playbook:
```yaml
---
- name: Test NETCONF on Microwave links by setting transmitted power level
  hosts: my_microwave_ne

  roles:

    - role: ncpwd
      vars:
        ncpwd_password: NotSoSecret123*
```

The [test_ansible](https://github.com/jrebiffe/test_ansible) repository
usable as project on AWX.

License
-------

MIT

Author Information
------------------

Jean Rebiffe, Orange Innovation Networks
