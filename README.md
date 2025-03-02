# 🛡️ Iron Shield

### Sistema avanzado de detección y eliminación de botnets en redes empresariales con **IPv6** y **Proxmox**  

---
## 📖 Descripción

**Iron Shield** es una solución especializada en la detección y eliminación de botnets en entornos empresariales. Se basa en el análisis profundo de tráfico de red en **IPv6**, utilizando herramientas avanzadas de monitoreo y respuesta a incidentes. Su implementación en **Proxmox** permite un despliegue eficiente en infraestructuras virtualizadas, garantizando un alto nivel de seguridad y escalabilidad.  

Este sistema se compone de tres módulos principales:
- **Monitorización**: Captura y análisis del tráfico en tiempo real.
- **Detección**: Identificación de patrones maliciosos mediante IDS/IPS.
- **Mitigación**: Respuesta automática ante amenazas detectadas.

---
## 🛠️ Tecnologías utilizadas

| Tecnología | Función en el proyecto |
| -----------| ---------------------- |
| **Proxmox VE** | Virtualización y gestión de máquinas |
| **Suricata**  | Sistema de detección y prevención de intrusiones (IDS/IPS) |
| **Zeek (Bro)** | Análisis profundo del tráfico de red |
| **Python & Scapy** | Captura y procesamiento de paquetes en IPv6 |
| **Grafana & Prometheus** | Visualización de métricas y alertas de seguridad |

---
## 📊 Dashboard
Para visualizar las métricas de la red en **Grafana**, accede a: 
⛓️‍💥 `http://<IP_DEL_SERVIDOR>:3000`
Credenciales por defecto:
- **Usuario**: `iron_admin`
- **Contraseña**: `iron_password`

---

## 🏗️ Roadmap
✅ **Version 1.0** - Instalación de proxmox y configuracion de suricata.

## 🤝 Contribuciones
Las contribuciones son bienvenidas. Si deseas colaborar:
1. Haz un fork del repositorio.
2. Crea una nueva rama (`git checkout -b feature-nueva`).
3. Sube tus cambios (`git commit -m "Descripción del cambio"`).
4. Envía un Pull Request.

## 📜 Licencia
Este proyecto está bajo la licencia MIT. Consulta el archivo LICENSE para más detalles.
