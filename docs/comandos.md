# Comandos — Infraestructura 3

## Cisco / red

~~~text
show ip interface brief
show ip route
show vlan brief
show interfaces trunk
~~~

## FortiGate

~~~text
get system interface
get router info routing-table all
get system arp
show firewall policy
show firewall vip
get vpn ipsec tunnel summary
~~~

## Validaciones de red

~~~bash
ip addr
ip route
ping 172.16.50.1
traceroute 172.16.60.2
~~~

## Validación HTTPS

~~~bash
curl -kI https://<PUBLIC-IP>/
~~~

## Validación SSH

~~~bash
nc -nvz -w 5 172.16.60.2 22
ssh <usuario>@172.16.60.2
~~~

La política esperada es que TCP/22 no sea accesible directamente desde WAN y que el acceso administrativo se realice mediante la Remote-Site VPN.
