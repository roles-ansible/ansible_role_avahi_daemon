# ansible_role_template
Template for Ansible roles

Netfilter rules
---------------

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

* https://www.avahi.org/
* https://github.com/lathiat/avahi

* http://www.dns-sd.org/ServiceTypes.html
