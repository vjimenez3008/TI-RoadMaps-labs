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