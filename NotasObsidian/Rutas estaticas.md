
# 📘 Routing Estático

### 🔑 Concepto

- **Routing estático** = el administrador configura manualmente las rutas en los routers.
    
- No hay aprendizaje automático (como en RIP, OSPF, EIGRP).
    
- Es simple, consume pocos recursos, pero **no se adapta solo a cambios de red**.
    

---

### 📌 Sintaxis en Cisco IOS

`Router(config)# ip route <red_destino> <máscara> <ip_next_hop | interfaz_salida>`

- `<red_destino>` → Red a la que quiero llegar.
    
- `<máscara>` → Máscara de esa red.
    
- `<ip_next_hop>` → IP del siguiente router hacia esa red.
    
- `<interfaz_salida>` → Alternativa: especificar la interfaz local.
    

---

### Ejemplo

`Router(config)# ip route 192.168.2.0 255.255.255.0 10.0.0.2`

👉 Significa: _Para llegar a la red 192.168.2.0/24, envía el tráfico al siguiente salto 10.0.0.2_.

---

# 🖥️ Conectar 2 Routers en Packet Tracer

### 🔧 Topología básica

`PC1 ---- R1 ---- R2 ---- PC2`

- PC1 en la red **192.168.1.0/24**
    
- PC2 en la red **192.168.2.0/24**
    
- Enlace entre routers **10.0.0.0/30**
    

---

### ⚙️ Configuración paso a paso

#### 1. Configurar R1

`R1> enable R1# configure terminal R1(config)# interface g0/0 R1(config-if)# ip address 192.168.1.1 255.255.255.0 R1(config-if)# no shutdown  R1(config)# interface g0/1 R1(config-if)# ip address 10.0.0.1 255.255.255.252 R1(config-if)# no shutdown`

#### 2. Configurar R2

`R2> enable R2# configure terminal R2(config)# interface g0/0 R2(config-if)# ip address 192.168.2.1 255.255.255.0 R2(config-if)# no shutdown  R2(config)# interface g0/1 R2(config-if)# ip address 10.0.0.2 255.255.255.252 R2(config-if)# no shutdown`

---

### 🛣️ Configurar rutas estáticas

En **R1** (para llegar a la red de PC2):

`R1(config)# ip route 192.168.2.0 255.255.255.0 10.0.0.2`

En **R2** (para llegar a la red de PC1):

`R2(config)# ip route 192.168.1.0 255.255.255.0 10.0.0.1`

---

### 💻 Configurar PCs

- **PC1**
    
    - IP: `192.168.1.10`
        
    - Mask: `255.255.255.0`
        
    - Gateway: `192.168.1.1`
        
- **PC2**
    
    - IP: `192.168.2.10`
        
    - Mask: `255.255.255.0`
        
    - Gateway: `192.168.2.1`
        

---

### ✅ Verificación

- Desde **PC1**:
    

`ping 192.168.2.10`

- Desde **PC2**:
    

`ping 192.168.1.10`

Si todo está bien → tendrás comunicación entre las PCs pasando por los **2 routers con rutas estáticas**. 🚀




# 📌 ¿Qué es CGNAT?

- **Carrier-Grade NAT** = NAT a nivel del **proveedor de Internet (ISP)**.
    
- El ISP pone a **muchos clientes detrás de una sola IP pública**, usando NAT en sus equipos centrales.
    
- Así ahorran direcciones IPv4 (que ya están casi agotadas).
    

👉 En vez de que tu router tenga una **IP pública única**, el ISP te da una **IP privada interna** (como 10.x.x.x, 100.64.x.x o 172.16.x.x).  
Luego, su router gigante hace NAT y sale con una IP pública compartida con cientos de clientes.

---

# 📌 Ejemplo comparativo

### 🔹 Sin CGNAT

- Tu router recibe del ISP: **IP pública real (ej. 201.50.25.10)**.
    
- Puedes abrir puertos (port forwarding) y acceder desde fuera.
    

`[Tu PC 192.168.1.100] → [Router 201.50.25.10] → Internet`

---

### 🔹 Con CGNAT

- Tu router recibe del ISP: **IP privada (ej. 100.64.5.25)**.
    
- El ISP hace NAT hacia una IP pública compartida (ej. 201.50.25.10).
    
- Desde fuera, **no puedes distinguir cuál de todos los clientes detrás de esa IP es el tuyo**.
    
- Por eso: **no funciona port forwarding**, no puedes exponer un DVR o escritorio remoto directamente.
    

`[Tu PC 192.168.1.100] → [Router 100.64.5.25] → [NAT ISP 201.50.25.10] → Internet`

---

# 📌 Señales de que tienes CGNAT

1. Tu router muestra una IP WAN que empieza con:
    
    - `100.64.0.0 – 100.127.255.255` (rango reservado para CGNAT).
        
    - O alguna de las privadas: `10.x.x.x`, `172.16–31.x.x`, `192.168.x.x`.
        
    - Si ves eso, no tienes IP pública real.
        
2. Aunque abras puertos en tu router, desde fuera nunca funcionan.
    
3. Si haces “cuál es mi IP” en Google → te da una distinta a la que ves en tu router.
    

---

# 📌 Soluciones si tienes CGNAT

1. **Pedir al ISP una IP pública fija o dinámica** (a veces cuesta extra 💰).
    
2. Usar **DDNS** → pero solo funciona si tu ISP te da una IP pública, aunque sea dinámica.
    
3. Usar servicios **P2P/cloud** (cámaras, TeamViewer, AnyDesk, etc.).
    
4. Montar una **VPN inversa hacia un servidor en la nube**:
    
    - Tu red local abre un túnel hacia un servidor con IP pública (AWS, Oracle, etc.).
        
    - Desde fuera te conectas a ese servidor y de ahí entras a tu red.
        

---

# 📌 Resumen

- CGNAT = el ISP mete a muchos clientes detrás de una sola IP pública.
    
- Beneficia al ISP porque ahorra IPv4.
    
- Perjudica al usuario porque **rompe el acceso remoto directo**.
    
- Soluciones: IP pública, P2P de los equipos o túneles VPN hacia la nube.