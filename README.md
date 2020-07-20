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
| `install_path`     | Where to extract Xonotic server sources                                                      | `/opt/`                                     |
| `server_name`     | The public description of the Xonotic server                                                      | `Welcome to my Xonotic Server`                                     |
| `make_public`     | Set if the server will be registered or not in upstream servers catalogue                                                      | `0`                                     |
| `rcon_password`     | The Xonotic server remote console password                                                      | empty (= disabled)                                     |
| `welcome_message`     | The username of the user that will be named admin when joining                                                      | `Welcome!`                                     |
| `extra_configuration`     | Any other xonotic configuration in format `key value` (one per line), see https://gitlab.com/xonotic/xonotic/blob/master/server/server.cfg                                                       | empty                                     |

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
        - nautik1.xonotic
```

Sample inventory:

```
all:
  hosts:
    <ip-or-hostname>:
  vars:
    xonotic_version: 0.8.2
```

License
-------

[WTFPL](https://en.wikipedia.org/wiki/WTFPL)
