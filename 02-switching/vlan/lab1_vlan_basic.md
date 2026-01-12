#Sin VLANs

[ PC-A ] ---\
[ PC-B ] ---- SWITCH ---- broadcast a todos
[ PC-C ] ---/


#Con VLANs

VLAN 10: PC-A, PC-B
VLAN 20: PC-C

Broadcast separado

#Cada VLAN = un dominio de broadcast

#Lab mental: VLAN básica

        ┌───────────┐
 PC-A ──┤           │
        │  SWITCH   │
 PC-B ──┤           │
        └───────────┘

VLAN 10 → PC-A
VLAN 20 → PC-B


#Resultado esperado:

* PC-A <-> PC-A VLAN: ✓
* PC-B <-> PC-B VLAN distinta:Ⅹ

