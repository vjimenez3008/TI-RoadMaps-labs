
# 📘 **15 Comandos de soporte técnico en redes (Windows)**

---

## 🔹 1. Ver configuración de red

`ipconfig /all`

📌 Muestra toda la configuración: IP, máscara, gateway, DNS, adaptadores.  
👉 Primer comando en cualquier diagnóstico.

---

## 🔹 2. Liberar dirección IP

`ipconfig /release`

📌 Libera la IP que el equipo tiene asignada (DHCP).  
👉 Útil cuando hay conflictos de IP.

---

## 🔹 3. Renovar dirección IP

`ipconfig /renew`

📌 Solicita una nueva IP al servidor DHCP (generalmente el router).  
👉 Se usa después de `/release`.

---

## 🔹 4. Vaciar caché DNS

`ipconfig /flushdns`

📌 Borra los registros DNS guardados en caché.  
👉 Soluciona errores cuando un dominio no carga.

---

## 🔹 5. Mostrar caché DNS

`ipconfig /displaydns`

📌 Muestra los registros DNS que el equipo tiene guardados.  
👉 Útil para ver a qué IP se resolvió un dominio.

---

## 🔹 6. Probar conectividad con ping

`ping 8.8.8.8`

📌 Envía paquetes ICMP para probar si hay conexión.  
👉 Sirve para verificar si llegas a un host o IP.

---

## 🔹 7. Probar resolución de nombres

`ping www.google.com`

📌 Igual que ping, pero prueba que el **DNS funcione**.  
👉 Si falla por nombre pero no por IP → es problema de DNS.

---

## 🔹 8. Rastrear la ruta de un paquete

`tracert www.google.com`

📌 Muestra todos los “saltos” (routers) hasta llegar al destino.  
👉 Identifica dónde se corta la conexión (LAN, ISP, Internet).

---

## 🔹 9. Probar conectividad con más control

`Test-NetConnection www.google.com -Port 80`

📌 (PowerShell) Prueba conexión a un host y puerto específico.  
👉 Ejemplo: probar si el puerto 3389 (RDP) está accesible.

---

## 🔹 10. Ver tabla de enrutamiento

`route print`

📌 Lista las rutas que el sistema usa para decidir por dónde enviar paquetes.  
👉 Útil en redes con varias interfaces.

---

## 🔹 11. Ver conexiones y puertos abiertos

`netstat -ano`

📌 Muestra conexiones activas, puertos en escucha y procesos (PID).  
👉 Ayuda a detectar si un servicio está corriendo o si hay conexiones sospechosas.

---

## 🔹 12. Ver qué proceso usa un puerto

`tasklist /fi "PID eq 1234"`

📌 Muestra qué programa corresponde a un ID de proceso (PID).  
👉 Combínalo con `netstat -ano` para identificar aplicaciones que usan la red.

---

## 🔹 13. Probar resolución DNS manual

`nslookup www.google.com`

📌 Consulta manualmente un servidor DNS para resolver un dominio.  
👉 Útil cuando sospechas que el DNS del sistema está fallando.

---

## 🔹 14. Escanear ARP (quién está en la red)

`arp -a`

📌 Lista todas las direcciones IP y MAC que tu equipo conoce en la red local.  
👉 Útil para detectar dispositivos conectados o conflictos de IP.

---

## 🔹 15. Resetear la pila TCP/IP

`netsh int ip reset`

📌 Reinicia la configuración TCP/IP a los valores por defecto.  
👉 Soluciona errores de red persistentes (como “sin acceso a Internet”).

---

# 📌 Cómo estudiarlos

1. Cada día prueba 2–3 comandos en tu propia PC.
    
2. Haz un mini-laboratorio: desconecta Internet, cambia IP, apaga DNS para ver qué pasa.
    
3. Documenta ejemplos reales de salida → así los entiendes mejor.
    

---

✅ Con estos 15 comandos ya tienes el **kit básico de un técnico de soporte en redes Windows**.  
Más adelante te puedo armar el **nivel 2** con automatización en PowerShell (scripts que revisan conectividad y corrigen problemas automáticamente).