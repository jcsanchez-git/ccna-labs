## Objetivo
Comprender cómo las VLANs separan dominios de broadcast.

Este módulo cubre los fundamentos de VLANs:
- Segmentación lógica
- Dominios de broadcast
- VLAN 1
- Puertos access y trunk

No incluye aún:
- Inter-VLAN routing
- Trunking avanzado

## Diseño
Un switch L2 con dos VLANs:
- VLAN 10: USERS
- VLAN 20: ADMIN



Sin VLANs:

[ PC-A ] ---\
[ PC-B ] ---- SWITCH ---- broadcast a todos
[ PC-C ] ---/

Con VLANs:

VLAN 10: PC-A, PC-B
VLAN 20: PC-C

Broadcast separado

Cada VLAN = un dominio de broadcast

Lab mental: VLAN básica

        ┌───────────┐
 PC-A ──┤           │
        │  SWITCH   │
 PC-B ──┤           │
        └───────────┘

VLAN 10 → PC-A
VLAN 20 → PC-B



##Resultado esperado:

* Hosts dentro de la misma VLAN se comunican: ✓
* Hosts en VLANs distintas NO se comunican: ✗

## Comportamiento esperado
- Hosts en la misma VLAN se comunican.
- Hosts en VLANs distintas no se comunican.

## Conclusión
## Conclusión
Este lab demuestra que las VLANs permiten dividir un switch físico
en múltiples dominios de broadcast lógicos, mejorando el orden,
la seguridad y la escalabilidad de la red sin requerir hardware adicional.

