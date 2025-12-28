## 📘 **Protocolos: TLS e IPSec**

🔐 **TLS (Transport Layer Security)**

- Se usa para proteger la comunicación en aplicaciones como **HTTPS, correo electrónico, VoIP**.
    
- Garantiza:
    
    - **Confidencialidad** → Encriptación.
        
    - **Integridad** → Que los datos no sean alterados.
        
    - **Autenticación** → Certificados digitales.
        

🌍 Ejemplo: Cuando entras a un sitio web con `https://`, tu navegador usa TLS para asegurar la conexión.

---

🔐 **IPSec (Internet Protocol Security)**

- Se utiliza para asegurar la **comunicación a nivel de red (capa 3 - IP)**.
    
- Puede cifrar **todo el tráfico entre dos dispositivos o redes**.
    
- Funciona en 2 modos:
    
    - **Transporte** → Solo cifra la carga útil del paquete.
        
    - **Túnel** → Cifra el paquete IP completo (usado en VPNs).
        

🌍 Ejemplo: Una VPN de empresa con IPSec cifra todo tu tráfico antes de salir a internet.

---

## 🖥️ **Simulación VPN**

1. Imagina que trabajas desde tu casa y necesitas entrar a los servidores de tu empresa.
    
2. Sin VPN → Tu conexión viaja abierta por internet (riesgo de robo de datos).
    
3. Con VPN (ej. IPSec o SSL VPN) → Se crea un **túnel cifrado** entre tu PC y la red de la empresa.
    
4. Todo el tráfico (archivos, correos, aplicaciones internas) viaja seguro, como si estuvieras dentro de la oficina.
    

📌 Así, la VPN:

- Oculta tu IP real.
    
- Protege tus datos.
    
- Te da acceso remoto seguro.
    

---

## 🇬🇧 **Ejemplo de ticket en inglés**

> **Subject:** VPN Connection Issue
> 
> **Description:**  
> The VPN is not working because the authentication fails when trying to connect. I have verified my credentials, but the system keeps rejecting the login. Please check the VPN server configuration or reset my access.