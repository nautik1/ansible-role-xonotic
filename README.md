Ansible-role-xonotic
=====================

This role helps installing a Xonotic server.

Requirements
------------

Any debian-based linux should work, preferably Ubuntu 20.04.

Tested with:
- Xonotic 0.8.2
- Ansible 2.9.10
- Ubuntu 20.04 on [Gandi Cloud](https://www.gandi.net/fr/cloud)

Role Variables
--------------

| Variable              | Description                                                                                                  | Example                                   |
|-----------------------|--------------------------------------------------------------------------------------------------------------|-------------------------------------------|
| `xonotic_version`     | The version of the Xonotic server to download and install                                                      | `5.3*`                                     |
| `server_name`     | The public name of the Xonotic server                                                      | `Xonotic server`                                     |
| `server_description`     | The public description of the Xonotic server                                                      | `Welcome to my Xonotic Server`                                     |
| `bind_address`     | The ip address to bind to                                                      | `0.0.0.0`                                     |
| `bind_port`     | The server port on which Xonotic will be exposed                                                      | `30000`                                     |
| `admin_username`     | The username of the user that will be named admin when joining                                                      | empty                                     |
| `extra_configuration`     | Any other xonotic configuration in format `key=value` (one per line), see https://wiki.xonotic.net/Xonotic.conf                                                       | empty                                     |

Dependencies
------------

No dependency, Xonotic downloaded from their website: https://xonotic.org/download/

Example Playbook
----------------

Sample playbook:

```
    - name: Install Xonotic
      hosts: all
      roles:
        - nautik1.teeworlds
```

Sample inventory:

```
all:
  hosts:
    <ip-or-hostname>:
  vars:
    xonotic_version: 5.3*
```

License
-------

[WTFPL](https://en.wikipedia.org/wiki/WTFPL)
