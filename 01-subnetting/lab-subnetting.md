# Lab – Subnetting en GNS3

## Objetivo
Demostrar subnetting /26 y conectividad entre dos subredes usando un router.

## Topología
PC-A ---- R1 ---- PC-B

## Subredes calculadas
| Subred | Network           | Primer host       | Último host        | Broadcast         |
|-------|-------------------|-------------------|--------------------|-------------------|
| A     | 192.168.50.0/26   | 192.168.50.1      | 192.168.50.62      | 192.168.50.63    |
| B     | 192.168.50.64/26  | 192.168.50.65     | 192.168.50.126     | 192.168.50.127   |

## Direccionamiento IP
- **R1 Fa0/0:** 192.168.50.1/26  
- **R1 Fa0/1:** 192.168.50.65/26  
- **PC-A:** 192.168.50.10 /26 — GW 192.168.50.1  
- **PC-B:** 192.168.50.70 /26 — GW 192.168.50.65  

## Configuración del router (relevante)
```text
interface fa0/0
 ip address 192.168.50.1 255.255.255.192
 no shutdown

interface fa0/1
 ip address 192.168.50.65 255.255.255.192
 no shutdown
