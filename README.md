Role Name
=========

An Ansible role that installs and configures [Wireguard](https://www.wireguard.com/) VPN.

Requirements
------------


Role Variables
--------------

    wg_start_method: "nm"

`wg_start_method` can be :
- `nm` for NetworkManager
- `wg-quick`
- `systemd-networkd`
- `netctl`
- `connman`

The selected method will be used to configure, start and/or enable wireguard interfaces for this host.

    wg_conf_directory: "/etc/wiregard"

`wg_conf_directory` is not mandatory and has different effects depending on the startup method selected

    wg_config:
      wg0:
        address: "10.0.0.1"
        endpoint: "1.1.1.1"
        port: 12345
        allowed_ips: "10.0.0.1/24"
        start: true
        enable: true

Dependencies
------------


Example Playbook
----------------


License
-------

MIT

Author Information
------------------

[Loïc Michaux](https://github.com/lmcx)
