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
| **Ngrok**  | Redireccion de puertos para conexion remota |

---

## 💻 Ngrok

Para poder conectarnos de manera remota desde fuera del centro hemos implementado ngrok como redirección de puertos.
Para la instalación deberemos seguir los siguientes pasos: 
- Crear una cuenta en [ngrok](https://dashboard.ngrok.com/login)
- Descargar ngrok
```bash
wget https://bin.equinox.io/c/bNyj1mQVY4c/ngrok-v3-stable-linux-amd64.tgz
```
- Descomprimir el archivo
```bash
tar -xvzf ngrok-v3-stable-linux-amd64.tgz -C /usr/local/bin/
```
- Añadir nuestro token
```bash
ngrok config add-authtoken <TokenEnPerfil>
```
- Crear el archivo ngrok.service en "/etc/systemd/system/ngrok.service"
```bash
[Unit]
Description=Ngrok Tunnel Service
After=network.target

[Service]
ExecStart=/usr/local/bin/ngrok tcp 22
Restart=always
User=root
WorkingDirectory=/usr/local/bin

[Install]
WantedBy=multi-user.target
```
- Reiniciar daemon
```bash
systemctl restart daemon
```
- Reiniciar el ngrok
```
systemctl restart ngrok.servive
```
- Hacer un status para saber si esta activo
```
systemctl status ngrok.servive
```
- Ir a la pagina web y en endpoints copiar despues del `tcp://`
```bash
0.tcp.eu.ngrok.io:11296
```
- Conectarnos mediante ssh con el siguiente comando.
```bash
ssh -L 8006:localhost:8006 root@7.tcp.eu.ngrok.io -p 19089
```

---

## 📊 Dashboard
Para visualizar las métricas de la red en **Grafana**, accede a: <br>
⛓️‍💥 `http://<IP_DEL_SERVIDOR>:3000` <br>
Credenciales por defecto:
- **Usuario**: `iron_admin`
- **Contraseña**: `iron_password`

---

## 🏗️ Roadmap
✅ **Version 1.0** - Instalación de proxmox y configuracion de suricata.
✅ **Version 1.1** - Configuracion de pfsense y VLAN's


## 🤝 Contribuciones
Las contribuciones son bienvenidas. Si deseas colaborar:
1. Haz un fork del repositorio.
2. Crea una nueva rama (`git checkout -b feature-nueva`).
3. Sube tus cambios (`git commit -m "Descripción del cambio"`).
4. Envía un Pull Request.

## 📜 Licencia
Este proyecto está bajo la licencia MIT. Consulta el archivo LICENSE para más detalles.
