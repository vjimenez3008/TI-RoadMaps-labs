
# 📌 1. **Port Forwarding con IP pública (mejor con DDNS)**

- Habilitas **port forwarding** en tu router, redirigiendo los puertos de tu DVR/NVR/cámara IP hacia Internet.
    
- Ejemplo:
    
    - Puerto HTTP (80 o 8080) → para ver vía navegador.
        
    - Puerto RTSP (554) → para apps de video.
        
    - Puerto del fabricante (ej. 8000, 37777, etc. depende de la marca).
        
- Si tu IP pública es dinámica, configuras un **DDNS** (ej. `midvr.ddns.net`).
    
- En el celular, en la app de la cámara, pones:
    
    - **Host:** `midvr.ddns.net`
        
    - **Puerto:** el que abriste.
        

👉 Pros: funciona directo y sin terceros.  
👉 Contras: no sirve si tienes **CGNAT** y requiere buena seguridad (usuario/contraseña fuerte, cambiar puertos).

---

# 📌 2. **VPN hacia tu red**

- Configuras un servidor **VPN** en tu router (si lo soporta) o en un equipo local (ej. OpenVPN, WireGuard).
    
- Desde tu celular te conectas a la VPN → quedas “dentro” de tu red local.
    
- Así puedes ver las cámaras como si estuvieras en la misma WiFi.
    

👉 Pros: más seguro, no necesitas abrir puertos del DVR directamente.  
👉 Contras: configuración más técnica y algunos routers básicos no soportan VPN.

---

# 📌 3. **Túnel inverso con servidor intermedio**

- Si tienes **CGNAT o limitaciones**, puedes usar un servidor en la nube (AWS, Oracle, etc.) como puente.
    
- El DVR o una PC local abre una conexión hacia el servidor en la nube (VPN inversa, SSH túnel).
    
- Luego, tu celular se conecta a ese servidor para llegar a las cámaras.
    

👉 Pros: funciona aunque no tengas IP pública ni P2P.  
👉 Contras: requiere conocimientos de redes y posiblemente pagar un servidor cloud.

---

# 📌 Resumen rápido

- ✅ **IP pública + Port Forwarding + DDNS** → la opción clásica.
    
- ✅ **VPN** → la opción más segura.