       VLAN 10,20
   ┌──────────────┐
   │   Switch A   │
   └──────┬───────┘
          │  TRUNK (802.1Q)
   ┌──────┴───────┐
   │   Switch B   │
   └──────────────┘
       VLAN 10,20

## Objetivo
Comprender cómo un trunk transporta múltiples VLANs.

## Diseño
Dos switches conectados por un enlace trunk.
VLANs presentes en ambos extremos.

## Tráfico esperado
- VLAN 10 → VLAN 10 (OK)
- VLAN 10 → VLAN 20 (NO)

## Riesgos
Una mala configuración de VLAN nativa puede causar tráfico no deseado.
