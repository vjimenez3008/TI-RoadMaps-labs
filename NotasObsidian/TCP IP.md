## 📌 Capas del modelo TCP/IP

El modelo TCP/IP tiene **4 capas principales** (a veces se compara con las 7 del modelo OSI).

---

### **1. Capa de Aplicación**

- **Función:** Permite la interacción entre el usuario y la red.
    
- Se encarga de los **protocolos de alto nivel** que usan las aplicaciones para comunicarse.
    
- Aquí se encuentran los **servicios de red** (correo, web, transferencia de archivos, etc.).
    
- **Protocolos más importantes:**
    
    - **HTTP / HTTPS** → Navegación web
        
    - **FTP, SFTP** → Transferencia de archivos
        
    - **SMTP, IMAP, POP3** → Correo electrónico
        
    - **DNS** → Traduce nombres de dominio a direcciones IP
        
    - **DHCP** → Asigna direcciones IP automáticamente
        
- 🔑 En esta capa es donde se define **qué servicio o aplicación quiere el usuario**.
    

---

### **2. Capa de Transporte**

- **Función:** Garantizar que los datos lleguen desde la aplicación de origen hasta la aplicación de destino.
    
- Divide los datos en **segmentos** y controla la comunicación entre procesos.
    
- **Protocolos clave:**
    
    - **TCP (Transmission Control Protocol)**
        
        - Confiable (garantiza entrega de datos)
            
        - Usa confirmaciones (ACKs), control de errores, control de flujo
            
        - Ejemplo: navegación web, correo electrónico
            
    - **UDP (User Datagram Protocol)**
        
        - Más rápido pero **no confiable** (no garantiza entrega ni orden)
            
        - Ideal para streaming, juegos online, VoIP
            
- 🔑 Aquí se gestiona **la confiabilidad y el orden** de los datos.
    

---

### **3. Capa de Internet**

- **Función:** Encargada del **direccionamiento y enrutamiento** de los paquetes en la red.
    
- Define **cómo viajan los datos** de un dispositivo a otro (aunque estén en redes diferentes).
    
- La unidad de datos aquí se llama **paquete**.
    
- **Protocolos principales:**
    
    - **IP (Internet Protocol):**
        
        - **IPv4 (32 bits)** y **IPv6 (128 bits)**
            
        - Direccionamiento lógico (ejemplo: 192.168.1.1 o 2001:db8::1)
            
    - **ICMP (Internet Control Message Protocol):**
        
        - Para mensajes de error y diagnóstico (ejemplo: comando `ping`)
            
    - **ARP (Address Resolution Protocol):**
        
        - Traduce direcciones IP a direcciones MAC (en LAN)
            
    - **RARP (Reverse ARP):**
        
        - Hace lo contrario (MAC → IP, aunque ya casi no se usa)
            
- 🔑 Aquí se asegura que **los datos lleguen al dispositivo correcto en la red**.
    

---

### **4. Capa de Acceso a la Red** (o **Enlace**)

- **Función:** Define cómo los datos viajan físicamente por el medio de transmisión.
    
- Incluye tanto el **hardware** (tarjetas de red, cables, switches, Wi-Fi) como los protocolos de acceso.
    
- La unidad de datos aquí se llama **trama** (frame).
    
- **Protocolos y tecnologías comunes:**
    
    - **Ethernet** (redes cableadas LAN)
        
    - **Wi-Fi (IEEE 802.11)**
        
    - **PPP (Point-to-Point Protocol)**
        
    - **DSL, fibra óptica, 5G**
        
- También define la **dirección física** (dirección MAC de la tarjeta de red).
    
- 🔑 Aquí los datos se convierten en **bits (0s y 1s)** y viajan por el medio.
    

---

## 📊 Comparación con el modelo OSI

El modelo OSI tiene 7 capas, TCP/IP solo 4. Se pueden mapear así:

|Modelo OSI|Modelo TCP/IP|
|---|---|
|7. Aplicación|4. Aplicación|
|6. Presentación|4. Aplicación|
|5. Sesión|4. Aplicación|
|4. Transporte|3. Transporte|
|3. Red|2. Internet|
|2. Enlace de Datos|1. Acceso a la Red|
|1. Física|1. Acceso a la Red|

---

## 📌 Ejemplo práctico: Visitar una página web

1. **Aplicación:** Escribes `www.google.com` en tu navegador → Se usa **HTTP/HTTPS** y **DNS**.
    
2. **Transporte:** TCP divide la petición en segmentos y asegura que se entreguen correctamente.
    
3. **Internet:** IP asigna direcciones origen/destino y enruta los paquetes por Internet.
    
4. **Acceso a red:** La tarjeta de red envía los datos en tramas Ethernet/Wi-Fi como bits.
    

