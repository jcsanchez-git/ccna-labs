# Subnetting – Teoría esencial (CCNA 200-301)

## ¿Qué es subnetting?
Subnetting es el proceso de dividir una red IP en múltiples subredes más pequeñas.

Se utiliza para:
- Optimizar el uso de direcciones IP
- Mejorar el rendimiento
- Separar dominios de broadcast

---

## IPv4 básico
- IPv4 tiene 32 bits
- Se divide en 4 octetos (8 bits cada uno)
- Ejemplo: 192.168.1.0/24

---

## Máscara de red
La máscara define qué parte es red y qué parte es host.

Ejemplos comunes:
- /24 → 255.255.255.0
- /26 → 255.255.255.192
- /30 → 255.255.255.252

---

## Regla clave
- Subredes = 2^n
- Hosts por subred = 2^h – 2

Donde:
- n = bits prestados
- h = bits de host

---

## Ejemplo rápido
Red: 192.168.1.0/26

- Bits de host: 6
- Hosts por subred: 2^6 – 2 = 62
- Subredes: 4
