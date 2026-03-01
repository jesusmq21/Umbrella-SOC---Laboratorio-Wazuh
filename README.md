# Umbrella SOC - Laboratorio Wazuh

## 🛡️ Descripción
**Umbrella SOC** es un script que inicia automáticamente un laboratorio SOC completo basado en Wazuh, levantando:

- **Wazuh Manager**  
- **Wazuh Indexer**  
- **Wazuh Dashboard**  

y abre el Dashboard en el navegador de manera automática.  

Con un solo comando (`iniciar umbrella`), tu laboratorio queda **100% operativo**, incluyendo verificación de servicios y puertos.

---
## 📌 Requisitos

- Ubuntu 22.04 o similar  
- Wazuh Manager, Indexer y Dashboard instalados  
- Node.js incluido en la instalación de Wazuh Dashboard  
- Permisos de sudo en la máquina virtual  

---

## 🚀 Instalación y uso

1. Copia el script a `/usr/local/bin/` y hazlo ejecutable:
   
sudo cp umbrella /usr/local/bin/
sudo chmod +x /usr/local/bin/umbrella

2.Ejecuta el script:

iniciar umbrella

3.Funcionalidades del script:

-Levanta los servicios:

--wazuh-manager

--wazuh-indexer

--wazuh-dashboard

-Verifica que cada servicio esté activo

-Confirma que el Dashboard escucha en el puerto 443

-Abre automáticamente el Dashboard en el navegador (si hay entorno gráfico)

-Muestra la URL de acceso

📷 Evidencia visual
1️⃣ Script ejecutándose

2️⃣ Dashboard cargando correctamente

3️⃣ Verificación del puerto 443

✅ Notas de seguridad

El script pide la contraseña 3 veces intencionalmente como medida de seguridad: incluso si un atacante conoce la contraseña, esto añade una capa adicional de protección.

Mantiene la sesión sudo viva mientras corre para que los comandos internos no requieran autenticación repetida.


🧭 Acceso al Dashboard

El script detecta automáticamente la IP de la máquina virtual y arma la URL:

https://<IP_DE_LA_VM>:443

Si hay entorno gráfico, se abre automáticamente en el navegador.


#⚙️ Comandos útiles

 Verificar servicios
systemctl status wazuh-manager wazuh-indexer wazuh-dashboard

 Verificar puertos
ss -tulnp | grep 443

 Revisar script
cat /usr/local/bin/umbrella

📜 Autor

Jesús Eduardo Machuca Quintero
SOC & Ciberseguridad | Laboratorio Wazuh



