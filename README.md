# P2 — Infraestructura 3
## HTTPS público y SSH protegido mediante Remote-Site VPN

**Asignatura:** Seguridad de Redes  
**Proyecto:** P2-Seguridad-Redes-VPN-FortiGate-2025-1331  
**Infraestructura:** 3 de 3  
**Autor:** Elian Sterling  
**Fecha:** octubre de 2026

### 🎥 Video de demostración

**[Ver demostración de Infraestructura 3](https://youtu.be/zlPV4KATfC4)**

### Objetivo

Construir un escenario donde **HTTPS/443** permanezca publicado para acceso público, mientras que **SSH/22** quede restringido al acceso administrativo mediante la Remote-Site VPN.

### Arquitectura

![Topología de Infraestructura 3](diagrams/topologia-infraestructura-3.svg)

### Direccionamiento principal

| Equipo / segmento | Dirección | Función |
|---|---|---|
| USER-01 / VLAN 10 | 172.16.50.0/25 | Red de usuarios |
| CISCO-R2 LAN | 172.16.50.1/25 | Gateway |
| CISCO-R2 WAN | 198.51.100.10/30 | Enlace WAN |
| ISP-R1 | 198.51.100.9/30 | Tránsito |
| FGT-01 WAN | 192.0.2.2/30 | Interfaz pública |
| FGT-01 Server-LAN | 172.16.60.1/28 | Gateway de servidores |
| WEB-01 | 172.16.60.2/28 | Web/SSH |
| Remote-Site VPN | 10.250.10.0/24 | Origen administrativo |

### Modelo de seguridad

| Servicio | Acceso |
|---|---|
| HTTPS / TCP 443 | Público mediante VIP/NAT |
| SSH / TCP 22 desde WAN | No permitido |
| SSH / TCP 22 desde 10.250.10.0/24 por VPN | Permitido |

### Contenido

- **[Documentación técnica](docs/infraestructura.md)**
- **[Comandos y validaciones](docs/comandos.md)**
- **[Evidencias gráficas](docs/evidencias.md)**
- **[Políticas sanitizadas](configs/politicas-sanitizadas.md)**
- **[Diagrama](diagrams/topologia-infraestructura-3.svg)**
- **[Capturas](evidencias/)**

### Seguridad

No se publican PSK, contraseñas, tokens ni claves privadas. Los valores sensibles se representan como `<REDACTED>`.
