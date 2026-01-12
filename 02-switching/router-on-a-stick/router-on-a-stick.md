# Router-on-a-Stick

## Descripción
Router-on-a-Stick es un método de inter-VLAN routing que permite
la comunicación entre VLANs mediante un único enlace físico
entre un switch y un router, utilizando etiquetado 802.1Q.

Cada VLAN se asocia a una subinterfaz lógica en el router,
la cual actúa como gateway para dicha VLAN.

## Funcionamiento
- El switch envía tráfico etiquetado (802.1Q)
- El router procesa cada VLAN mediante subinterfaces
- Cada subinterfaz actúa como gateway de su VLAN

## Diseño

VLAN 10 ─┐
VLAN 20 ─┼── Switch ── Trunk ── Router
VLAN 30 ─┘ |
Subinterfaces


- Cada VLAN → una subinterfaz
- Cada subinterfaz → un gateway
- Sin trunk → no existe Router-on-a-Stick

## Casos de uso
- Laboratorios
- Redes pequeñas
- Entornos educativos

## Limitaciones
- Rendimiento limitado
- Dependencia de un solo enlace
- Punto único de fallo
- No recomendado para redes medianas o grandes
