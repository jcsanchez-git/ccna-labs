## VLAN Hopping

### Descripción
VLAN Hopping es una vulnerabilidad de Capa 2 causada por una
configuración insegura de switches.

### Tipos de ataque
- Switch Spoofing
- Double Tagging

### Condiciones necesarias
- Puertos en modo dinámico
- Uso de VLAN 1 como nativa
- Trunks sin restricciones

### Impacto
- Pérdida de aislamiento entre VLANs
- Acceso no autorizado a segmentos internos

### Mitigaciones
- Deshabilitar DTP
- Usar VLAN nativa dedicada sin hosts
- Forzar puertos access
- Restringir VLANs en trunks
