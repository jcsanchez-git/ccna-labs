## Objetivo
Comprender cómo un trunk transporta múltiples VLANs.



## Diseño
Dos switches conectados por un enlace trunk.
VLANs presentes en ambos extremos.

       VLAN 10,20
   ┌──────────────┐
   │   Switch A   │
   └──────┬───────┘
          │  TRUNK (802.1Q)
   ┌──────┴───────┐
   │   Switch B   │
   └──────────────┘
       VLAN 10,20



## Tráfico esperado
- Tráfico entre la misma VLAN a través del trunk: OK
- Tráfico entre VLANs distintas sin routing: NO



## VLAN Nativa
La VLAN nativa es la VLAN que transporta tráfico sin etiquetar en un enlace trunk.
Por razones de seguridad, no se recomienda usar VLAN 1 ni asignar hosts a la VLAN nativa.

Una práctica común es crear una VLAN sin usuarios (ej. VLAN 999) y configurarla
como VLAN nativa para evitar fugas de tráfico o ataques de VLAN hopping.



## Riesgos
Una mala configuración de la VLAN nativa puede causar:
- Fugas de tráfico entre VLANs
- Problemas de conectividad
- Riesgos de seguridad en capa 2



## Diseño típico de switch bien asegurado
VLAN 10   → USERS
VLAN 20   → ADMINS
VLAN 30   → SERVERS
VLAN 99   → MGMT
VLAN 998  → UNUSED (puertos apagados)
VLAN 999  → NATIVE (fake)



## Puertos no utilizados
Los puertos no utilizados deben ser deshabilitados administrativamente
y asignados a una VLAN sin hosts ni acceso a la red (VLAN de cuarentena).

Esta práctica reduce riesgos de acceso no autorizado y ataques de capa 2.
