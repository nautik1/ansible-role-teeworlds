Ansible-Teeworlds
=================

This role helps installing a Teeworlds server.

Requirements
------------

Any debian-based linux using systemd should work, preferably Ubuntu 18.04.

Tested with:
- Teeworlds 0.7.5
- Ansible 2.9.7
- Ubuntu 18.04 on [Gandi Cloud](https://www.gandi.net/fr/cloud)

Role Variables
--------------

| Variable              | Description                                                                                                  | Example                                   |
|-----------------------|--------------------------------------------------------------------------------------------------------------|-------------------------------------------|
| `teeworlds_version`     | The version of Teeworlds server to download and install                                                      | `0.7.5`                                     |
| `teeworlds_server_name` | Name of the server displayed in-game                                                                         | `Another teeworlds server`                  |
| `install_path`          | Path within the server where to install teeworlds                                                            | `/opt/teeworlds`                            |
| `extra_configs`         | Any additional Teeworlds configuration to set. See https://www.teeworlds.com/?page=docs&wiki=server_settings | extra_configs: \|       sv_max_clients 15 |

Dependencies
------------

No external role used; Teeworlds server downloaded from https://downloads.teeworlds.com

Example Playbook and inventory
------------------------------

Sample playbook:

```
    - name: Install Teeworld
      hosts: all
      roles:
        - teeworld
```

Sample inventory:

```
all:
  hosts:
    <ip-or-hostname>:
  vars:
    teeworlds_version: 0.7.5
    teeworlds_server_name: Another teeworlds server
    install_path: /opt/teeworlds
    extra_configs: |
      sv_max_clients 15
```

License
-------

[WTFPL](https://en.wikipedia.org/wiki/WTFPL)
