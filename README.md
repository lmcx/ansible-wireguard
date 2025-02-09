Ansible Role: Wireguard
=======================

![CI](https://github.com/lmcx/ansible-wireguard/actions/workflows/ci.yml/badge.svg?branch=develop)

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

    wg_conf_directory: "/etc/wireguard"

`wg_conf_directory` is not mandatory and has different effects depending on the startup method selected

    wg_config:
      wg0:
        address: "10.0.0.1"
        endpoint: "{{ ansible_default_ipv4.address }}"
        port: 12345
        allowed_ips: "10.0.0.1/24"
        start: true
        enable: true
        unmanaged_peers:
          peer_zero:
            pubkey: "AAAAA"
            persistent_keepalive: 30
            allowed_ips:
              - "10.0.1.10/32"
              - "10.1.0.1/24"
            endpoint: "1.1.1.1"
            port: 11111
            psk: "BBBBBBB"
            psk_flags: 0

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
