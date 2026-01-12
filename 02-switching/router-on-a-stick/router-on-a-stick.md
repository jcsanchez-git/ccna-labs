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

## Diseño Router-on-Stick

VLAN 10 ─┐
VLAN 20 ─┼── Switch ── Trunk ── Router
VLAN 30 ─┘                 |
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

## Alternativas en producción
En redes medianas y grandes, el inter-VLAN routing se implementa
mediante switches de capa 3, utilizando interfaces VLAN (SVI),
lo que elimina cuellos de botella y mejora la escalabilidad.

## Diseño con Switch capa 3
          ┌───────────────┐
VLAN 10 ──┤               │
VLAN 20 ──┤  Switch L3    │  ← Inter-VLAN Routing
VLAN 30 ──┤               │
          └──────┬────────┘
                 │
             Core / Router WAN

- Cada VLAN → una SVI
- Cada subinterfaz → un Gateway
- El routing ocurre en el switch

## Diferencias claves
| Característica | RoAS    | Switch L3  |
| -------------- | ------- | ---------- |
| Enlace         | 1 trunk | Interno    |
| Gateway        | Router  | SVI        |
| Rendimiento    | Bajo    | Muy alto   |
| Escalabilidad  | Mala    | Excelente  |
| Uso real       | Labs    | Producción |

## Conclusión final
Por qué router-on-a-stick no es escalable
| Problema                          | Impacto              |
| --------------------------------- | -------------------- |
| Un solo enlace físico             | Cuello de botella    |
| Un solo router                    | Punto único de fallo |
| Todo el tráfico pasa por L2→L3→L2 | Latencia             |
| No aprovecha switching hardware   | Bajo rendimiento     |
