[![Galaxy](https://github.com/roles-ansible/ansible_role_avahi_daemon/raw/main/.github/galaxy.svg)](https://galaxy.ansible.com/do1jlr/avahi_daemon)
[![License](https://github.com/roles-ansible/ansible_role_avahi_daemon/raw/main/.github/license.svg)](https://github.com/roles-ansible/ansible_role_avahi_daemon/blob/main/LICENSE)

 ansible role avahi_daemon
===========================
Ansible role to install the avahi_daemon and optionally announce some services.

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
