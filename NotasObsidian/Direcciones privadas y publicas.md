# 📘 Día 3 – IPv4: Direcciones privadas y públicas

## 🌍 ¿Qué es IPv4?

- IPv4 = Internet Protocol version 4.
    
- Usa **32 bits** → permite aprox. **4.3 mil millones de direcciones**.
    
- Se representa en formato **decimal con puntos** (ejemplo: `192.168.1.10`).
    

---

## 🔹 Direcciones **Privadas** (RFC 1918)

Usadas **dentro de redes locales** (LAN). No son enrutable en Internet.  
Se comunican mediante **NAT** (Network Address Translation).

| Clase | Rango privado                 | Cantidad de IPs |
| ----- | ----------------------------- | --------------- |
| A     | 10.0.0.0 – 10.255.255.255     | ~16.7 millones  |
| B     | 172.16.0.0 – 172.31.255.255   | ~1 millón       |
| C     | 192.168.0.0 – 192.168.255.255 | ~65 mil         |

✅ Ejemplos:

- `10.0.1.15`
    
- `172.16.5.100`
    
- `192.168.100.3`
    

---

## 🔹 Direcciones **Públicas**

- Todas las que **no son privadas** ni reservadas.
    
- Asignadas por **ISP** (Proveedor de Internet).
    
- Son **enrutables en Internet**.
    

Ejemplo:

- `8.8.8.8` (Google DNS)
    
- `142.250.190.78` (un servidor de Google)
    

---

## 🔹 Reservadas (ejemplos especiales)

- `127.0.0.1` → **Loopback (localhost)**
    
- `169.254.x.x` → **APIPA** (asignación automática si falla DHCP)
    
- `0.0.0.0` → dirección no asignada
    

---

## 🖥️ Laboratorio práctico

1. Abre **CMD o PowerShell** y escribe:
    
    `ipconfig`
    
    → Identifica tu dirección privada.
    
2. Busca tu **IP pública** con:
    
    `curl ifconfig.me`
    
    o entrando a https://whatismyip.com.
    
3. Documenta ambas en tu nota:
    
    - IP privada: `192.168.1.x`
        
    - IP pública: `201.xx.xx.xx`
        

---

## 🇬🇧 Ejercicio en inglés

✍️ Escribe 3 frases en inglés:

- "My private IP address is 192.168.1.10."
    
- "A public IP address can be used on the Internet."
    
- "NAT allows private addresses to connect to the Internet."




# 📌 ¿Qué es Port Forwarding?

- También se llama **redirección de puertos** o **NAT estático**.
    
- Es una función de los routers que permite que un equipo externo en Internet pueda acceder a un servicio que está **dentro de tu red local (LAN)**.
    

👉 Recuerda: por defecto, **NAT bloquea conexiones entrantes** desde Internet. Port forwarding es la forma de decirle al router:

> “Si llega tráfico a este puerto público, mándalo al dispositivo X dentro de la LAN”.

---

# 📌 Ejemplo simple

- Tu PC (LAN): `192.168.1.100`
    
- Servicio: servidor web en puerto `80`.
    
- Router (WAN): IP pública `201.50.25.10`.
    

Si alguien desde Internet escribe:

`http://201.50.25.10:80`

→ el router recibe el tráfico en su puerto 80 y lo reenvía a `192.168.1.100:80`.

---

# 📌 Casos de uso típicos

- **Cámaras de seguridad / DVR / NVR**
    
- **Remote Desktop (RDP en puerto 3389)**
    
- **Servidores web locales (puerto 80/443)**
    
- **Videojuegos que requieren hosting**
    

---

# 📌 ¿Cómo abrir puertos en un router? (pasos generales)

Cada marca tiene su interfaz distinta, pero el flujo es siempre parecido:

### 1. Entrar al router

- Escribes en el navegador la puerta de enlace (ej. `192.168.1.1`).
    
- Ingresas usuario y contraseña (admin / admin en algunos casos, pero mejor cambiarlos).
    

### 2. Ubicar la sección NAT / Port Forwarding

- Puede estar en:
    
    - **NAT**
        
    - **Firewall**
        
    - **Virtual Server**
        
    - **Port Mapping**
        
    - **Applications & Gaming**
        

### 3. Crear una regla

- **Puerto externo (WAN):** el que usarán desde Internet (ej. 8080).
    
- **IP destino interna (LAN):** el equipo donde está el servicio (ej. 192.168.1.100).
    
- **Puerto interno:** donde escucha el servicio (ej. 80).
    
- **Protocolo:** TCP, UDP o ambos.
    

👉 Ejemplo de regla:

`WAN:201.50.25.10:8080 → LAN:192.168.1.100:80 (TCP)`

### 4. Guardar y aplicar cambios

### 5. (Opcional) Configurar DDNS

- Si tu IP pública es dinámica, asocia un dominio tipo `miempresa.dyndns.org`.
    

### 6. Probar desde fuera

- Usar `canyouseeme.org` o intentar acceder con el celular en 4G (no WiFi).
    

---

# 📌 Cosas a tener en cuenta

1. **IP pública real:** si estás en CGNAT → el port forwarding no sirve.
    
2. **Firewall:** asegúrate de que el router y el PC/dispositivo permitan conexiones en ese puerto.
    
3. **Seguridad:** nunca abras puertos sensibles (RDP 3389, SSH 22, MySQL 3306) sin protegerlos (VPN o cambiar puerto).
    

---

# 📌 Ejemplo real con Remote Desktop

- PC en LAN: `192.168.1.150` con RDP habilitado (puerto 3389).
    
- En router creas regla:
    

`WAN:201.50.25.10:4000 → LAN:192.168.1.150:3389 (TCP)`

- Desde fuera te conectas con:
    

`mstsc.exe → 201.50.25.10:4000`

Y entras al escritorio remoto de tu PC.

---

✅ En resumen: **Port forwarding es como decirle al router: cuando alguien toque este puerto de mi IP pública, mándalo a este dispositivo dentro de mi red.**