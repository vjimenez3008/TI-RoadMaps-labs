# 📘 Fundamentos de IPv6

### 🔑 ¿Qué es IPv6?

- **IPv6 (Internet Protocol version 6)** es la evolución de IPv4.
    
- Se creó porque las direcciones IPv4 (32 bits → ~4.3 mil millones de direcciones) se agotaron.
    
- IPv6 usa **128 bits**, lo que da una cantidad casi infinita de direcciones (≈ 340 undecillones).
    

---

### 📌 Características principales:

1. **Direcciones más largas**
    
    - IPv4: `192.168.1.1`
        
    - IPv6: `2001:0db8:85a3:0000:0000:8a2e:0370:7334` (se puede abreviar con `::`)
        
2. **Notación hexadecimal y bloques de 16 bits**
    
    - Ejemplo: `2001:db8::1`
        
3. **Tipos de direcciones**:
    
    - **Unicast** → dirección única para un host.
        
    - **Multicast** → para un grupo de hosts.
        
    - **Anycast** → la dirección se comparte entre varios dispositivos, pero responde el más cercano.
        
    - (No hay broadcast en IPv6).
        
4. **Autoconfiguración (SLAAC)**  
    Los dispositivos pueden obtener su dirección automáticamente sin servidor DHCP, usando la info del router.
    
5. **Link-Local (fe80::/10)**
    
    - Cada interfaz IPv6 genera una automáticamente.
        
    - Sirve para comunicación dentro de la misma red local (LAN).
        
6. **Mejor seguridad y movilidad**
    
    - IPSec es obligatorio.
        
    - Mejor soporte para IoT y redes móviles.
        

---

# 🖥️ Configurar IPv6 en Packet Tracer

👉 Te muestro los pasos básicos para practicar en **router, switch y PCs**.

---

### 1. **Configurar dirección IPv6 en un router**

`Router> enable Router# configure terminal Router(config)# interface g0/0 Router(config-if)# ipv6 address 2001:db8:1::1/64 Router(config-if)# ipv6 enable Router(config-if)# no shutdown`

---

### 2. **Configurar dirección IPv6 en una PC**

- En Packet Tracer → click en la PC → Desktop → **IP Configuration**
    
- Selecciona la pestaña **IPv6** y coloca:
    
    - IPv6 Address: `2001:db8:1::10`
        
    - Prefix: `64`
        
    - Default Gateway: `2001:db8:1::1`
        

---

### 3. **Verificar conectividad**

- Desde la PC:
    

`ping 2001:db8:1::1`

- Desde el router:
    

`ping 2001:db8:1::10`

---

### 4. **Configurar SLAAC (Autoconfiguración)**

En el router:

`Router(config)# interface g0/0 Router(config-if)# ipv6 address 2001:db8:1::/64 eui-64 Router(config-if)# ipv6 enable`

- Luego en la PC, deja “Obtain IPv6 address automatically”.
    
- La PC genera su propia dirección usando el prefijo del router (`2001:db8:1::/64`) + su identificador único.
    

---

### 5. **Comandos útiles**

- `show ipv6 interface brief` → ver direcciones IPv6 en interfaces.
    
- `ping ipv6 <direccion>` → hacer ping IPv6.
    
- `traceroute ipv6 <direccion>` → rastrear ruta.