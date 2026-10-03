# Políticas sanitizadas — Infraestructura 3

## HTTPS público

- Servicio: TCP/443.
- Destino lógico: WEB-01 172.16.60.2.
- Publicación: VIP/NAT en FGT-01.

## SSH administrativo

- Servicio: TCP/22.
- Origen WAN general: **denegado**.
- Origen autorizado: 10.250.10.0/24 mediante Remote-Site VPN.
- Destino: WEB-01 172.16.60.2.

## Principio de seguridad

El servicio público y el canal administrativo se mantienen separados. No se publican credenciales, PSK ni claves privadas.
