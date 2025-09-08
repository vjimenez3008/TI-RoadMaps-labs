# 📘 Subnetting básico (CIDR)

### 🔑 Concepto

- **CIDR (Classless Inter-Domain Routing)** = forma moderna de dividir redes.
    
- En vez de clases (A, B, C), usamos **prefijo** `/n` que indica **cuántos bits de red**.
    
- Ejemplo:
    
    - `192.168.1.0/24` → 24 bits para red, 8 bits para hosts.
        

---

### 📌 Cómo funciona

1. **Dirección IPv4** = 32 bits.
    
    - Ejemplo: `192.168.1.25` → en binario.
        
2. **Máscara de subred** → indica qué parte es **red** y qué parte es **hosts**.
    
    - `/24` = 255.255.255.0
        
    - `/26` = 255.255.255.192
        
3. **Cálculos importantes**:
    
    - Hosts posibles = `2^(bits_host) - 2`
        
    - Subredes = depende de los bits que le “robes” a los hosts.
        

---

### 📊 Ejemplos rápidos

- `192.168.1.0/24`
    
    - Máscara: 255.255.255.0
        
    - Host bits: 8 → `2^8 - 2 = 254 hosts`
        
    - Subred única.
        
- `192.168.1.0/26`
    
    - Máscara: 255.255.255.192
        
    - Host bits: 6 → `2^6 - 2 = 62 hosts`
        
    - Subredes: 4 (`/24` dividido en 4 bloques de /26).
        
- `10.0.0.0/30`
    
    - Máscara: 255.255.255.252
        
    - Host bits: 2 → `2^2 - 2 = 2 hosts`
        
    - Útil para enlaces punto a punto.
        

---

# 🖥️ Ejercicios con IP Calculator

👉 Cómo practicar fácilmente:

1. **Busca una “IP Calculator” online** o usa la integrada en Packet Tracer/CLI de Linux.
    
2. Ingresa una IP y máscara, ejemplo:
    
    - `192.168.10.0/27`
        
3. La calculadora te da:
    
    - **Rango de hosts**: 192.168.10.1 → 192.168.10.30
        
    - **Broadcast**: 192.168.10.31
        
    - **Hosts válidos**: 30
        

---

### ✍️ Ejercicios típicos:

1. Divide `192.168.1.0/24` en 8 subredes iguales.
    
    - Respuesta: `/27` (32 direcciones, 30 hosts cada una).
        
2. ¿Cuántos hosts soporta `172.16.0.0/20`?
    
    - Host bits = 12 → `2^12 - 2 = 4094 hosts`.
        
3. Para un enlace punto a punto ¿qué máscara usas?
    
    - `/30` (2 hosts).
        

---

### 💡 Tips para memorizar:

- `/24` = 254 hosts (red doméstica típica).
    
- `/30` = 2 hosts (enlace WAN).
    
- Mientras **más grande el prefijo (/n)** → menos hosts.
    
- Tabla rápida:
    

|Prefijo|Hosts posibles|
|---|---|
|/24|254|
|/25|126|
|/26|62|
|/27|30|
|/28|14|
|/29|6|
|/30|2|