subscription_manager
====================

Ansible role which manages RHSM registration.

The configuration of the role is done in such way that it should not be necessary
to change the role for any kind of configuration. All can be done either by
changing role parameters or by declaring completely new configuration as a
variable. That makes this role absolutely universal. See the examples below for
more details.

Please report any issues or send PR.


Examples
--------

```yaml
---

- name Example of how to register to RHSM
  hosts: myhost
  vars:
    # Specify RHMS credentials
    subscription_manager_rhsm_user: myuser
    subscription_manager_rhsm_pass: mypassword
  roles:
    - subscription_manager

- name Example of how to unregister from RHSM
  hosts: myhost
  vars:
    # Specify RHMS credentials
    subscription_manager_rhsm_user: myuser
    subscription_manager_rhsm_pass: mypassword
    # This wil make it unregister
    subscription_manager_state: absent
  roles:
    - subscription_manager
```


Role variables
--------------

List of variables used by the role:

```yaml
# RHSM credentials (must be provided by the user)
subscription_manager_rhsm_user: null
subscription_manager_rhsm_pass: null

# Default state (set to absent to unregister from RHSM)
subscription_manager_state: present

# Whether to auto attach
subscription_manager_auto_attach: yes

# Other optional paramets
#subscription_manager_activationkey: null
#subscription_manager_consumer_id: null
#subscription_manager_consumer_name: null
#subscription_manager_consumer_type: null
#subscription_manager_environment: null
#subscription_manager_force_register: null
#subscription_manager_org_id: null
#subscription_manager_pool_ids: null
#subscription_manager_pool: null
#subscription_manager_release: null
#subscription_manager_rhsm_baseurl: null
#subscription_manager_rhsm_repo_ca_cert: null
#subscription_manager_server_hostname: null
#subscription_manager_server_insecure: null
#subscription_manager_server_proxy_hostname: null
#subscription_manager_server_proxy_password: null
#subscription_manager_server_proxy_port: null
#subscription_manager_server_proxy_user: null
```


License
-------

MIT


Author
------

Jiri Tyr
