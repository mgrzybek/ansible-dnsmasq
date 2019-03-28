# ansible-dnsmasq

Role used to deploy a dnsmasq service on a server. Systemd-resolvd is disabled.

# Pre-requisites

N.A.


# Variables

Some options are auto-configured.

Packaging:

* ```dnsmasq_package_state```: upgrade already installed packages?
(default: "present")

You should give some upstream DNS serveurs:

* ```dnsmasq_main_conf.servers```: upstream servers.

# Dependances

None.

# Examples

Basec usage:

    - hosts: servers
      roles:
         - role: ansible-dnsmasq
      vars:
         dnsmasq_forwarding_zones:
           - name: consul
             forwarder:
               hostname: 127.0.0.1
               port: 8600
         dnsmasq_main_conf:
           servers:
             - 8.8.8.8
             - 8.8.4.4
           cache_size: 150


# License

GPL-3+

# Author Information

Mathieu GRZYBEK
