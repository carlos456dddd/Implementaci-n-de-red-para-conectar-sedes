# Implementacion-de-red-para-conectar-sedes
Proyecto académico
# Proyecto: Red Empresarial con OSPF – Packet Tracer

## 1. Objetivo
Conectar tres ubicaciones (sede central, laboratorio y oficina operativa) mediante una red WAN simulada, asegurando:
* Conectividad IP permanente  
* Enrutamiento dinámico vía OSPF  
* Redundancia ante caída de un enlace serial  

## 2. Topología
[R-Central] ‑‑‑Serial‑‑‑> [R-Lab] ‑‑‑Serial‑‑‑> [R-Operativa]
↕                        ↕                    ↕
Switch‑-PCs              Switch‑PCs           Switch‑PCs/Laptops

**Enlaces seriales (subredes /16):**
* 162.16.0.0 (Central ↔ Lab)  
* 162.17.0.0 (Lab ↔ Operativa)  
* 162.18.0.0 (Central ↔ Operativa)  

**LANs (/24):**
* 192.172.1.0 & 192.172.2.0 → Central  
* 192.172.3.0 → Laboratorio  
* 192.172.4.0 → Oficina Operativa  

## 3. Protocolo de enrutamiento
* OSPF área 0 en los tres routers  
* Router-ID manual para evitar duplicados  
* Métrica basada en ancho de banda (100 Mbps = costo 1)

## 4. Archivos del repo
| Archivo | Uso |
|---------|-----|
| `Implementación en Packet Tracer.pkt` | Escenario completo (listo para abrir) |
| `Implementación de una red para conectar las sedes de la empresa.pdf` | Explicación detallada del proyecto |

## 5. Validaciones
✔ Ping bidireccional entre todas las subredes  
✔ Traceroute muestra ruta de menor costo  
✔ Al apagar un puerto serial, OSPF recalcula y mantiene la comunicación (<40 s)  
