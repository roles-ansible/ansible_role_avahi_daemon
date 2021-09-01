[![Galaxy](https://github.com/roles-ansible/ansible_role_avahi_daemon/raw/main/.github/galaxy.svg)](https://galaxy.ansible.com/do1jlr/avahi_daemon)
[![License](https://github.com/roles-ansible/ansible_role_avahi_daemon/raw/main/.github/license.svg)](https://github.com/roles-ansible/ansible_role_avahi_daemon/blob/main/LICENSE)

 ansible role avahi_daemon
===========================
Ansible role to install the avahi_daemon and optionally announce some services.

 Variables
-----------
In the ``avahi_services`` variable you can define the services you want to announce.
Here is a list with available parameters:
 + ``service``: Service Name *(HTTP/SSH/...)* ***(required)***
 + ``port``: Service Port ***(required)***
 - ``name``: optional name to announce the Service
 - ``protocol``: ``any``/``ipv6``/``ipv4``
 - ``txt_records``: an array of txt records


Example:
```yaml
---
avahi_services:
  - service: 'SSH'
    port: 22
    protocol: 'any'
  - service: 'NFS'
    name: 'Filesharing Host %h'
    port: 2049
    protocol: 'ipv6'
    txt_records:
      - 'path=/path/to/nfsexport'
  - service: 'FTP'
    port: '21'
    protocol: 'ipv4'
    txt_records:
      - 'path=/ftppath'
      - 'u=ftpuser'
      - 'p=ftppass'
```

 Netfilter rules
---------------
Avahi is using multicast to announce services.
Do not forget to add netfilter rules for multicast dns.

Configuration example for `ferm`:

```
# mdns
daddr 224.0.0.251 proto udp dport 5353 ACCEPT;
daddr ff02::fb proto udp dport 5353 ACCEPT;
```

Links
-----

* http://dns-sd.org/
* http://www.multicastdns.org/

* https://kodi.wiki/view/Avahi_Zeroconf#Sample_service_configurations

* https://www.avahi.org/
* https://github.com/lathiat/avahi

* http://www.dns-sd.org/ServiceTypes.html
