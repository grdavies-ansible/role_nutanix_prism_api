Nutanix Role for Prism LCM Software & Firmware Updates
=========

This Ansible role invokes LCM to perform an inventory operation followed by software and firmware updates if necessary.


Input Variables
---------------

| Variable                              | Required | Default | Choices                                                                                | Comments                                                                                                                                                                                                     |
|---------------------------------------|----------|---------|----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| role_nutanix_prism_api_host           | yes      |         |                                                                                        | The IP address or FQDN for the Prism (Element or Central) to which you want to connect.                                                                                                                      |
| role_nutanix_prism_api_username       | no       | admin   |                                                                                        | A valid username with appropriate rights to access the Nutanix API.                                                                                                                                          |
| role_nutanix_prism_api_password       | yes      |         |                                                                                        | A valid password for the supplied username.                                                                                                                                                                  |
| role_nutanix_prism_api_port           | no       | 9440    |                                                                                        | The Prism TCP port.                                                                                                                                                                                          |
| role_nutanix_prism_api_validate_certs | no       | no      | true / false                                                                           | Whether to check if Prism UI certificates are valid.                                                                                                                                                         |
| role_nutanix_prism_api_debug          | no       | false   | true / false                                                                           | Whether or not to enable debugging output.                                                                                                                                                                   |

Returned Variables
------------------

| Variable                              | Values                                                                                 | Comments                                                                                                                                                                                                     |
|---------------------------------------|----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| role_nutanix_prism_api_endpoint_type  | 'pe' or 'pc'                                                                           | Indicates whether the API session was initiated against a Nutanix NCI cluster (Prism Element 'pe') or Nutanix NCM (Prism Central 'pc').                                                                      |

Dependencies
------------

- none

Example Playbook
----------------

This example playbook will invoke LCM on a specific cluster running only a software upgrade for "NCC"

```
- hosts: localhost
 roles:
   - role: grdavies.role_nutanix_prism_api
 vars:
   role_nutanix_prism_api_host: 10.38.185.37
   role_nutanix_prism_api_username: admin
   role_nutanix_prism_api_password: nx2Tech165!
```

License
-------

See LICENSE.md

Author Information
------------------

Ross Davies
