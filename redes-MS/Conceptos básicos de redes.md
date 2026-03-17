# 🌐 Networking Basics

## 📋 Referencia Rápida

| Concepto | Descripción breve |
|----------|-------------------|
| **IP Address** | Identificador único de un dispositivo en la red |
| **DNS** | Traduce nombres de dominio a direcciones IP |
| **DHCP** | Asigna IPs automáticamente a los dispositivos |
| **Ports** | Canal lógico para comunicación entre aplicaciones |
| **TCP** | Protocolo confiable, con confirmación de entrega |
| **UDP** | Protocolo rápido, sin confirmación de entrega |

---

## 🔢 IP Address — Dirección IP

Identificador único asignado a cada dispositivo conectado a una red.

### Versiones

| Versión | Ejemplo | Bits |
|---------|---------|------|
| **IPv4** | `192.168.1.1` | 32 bits |
| **IPv6** | `2001:0db8::1` | 128 bits |

### Tipos

```
IP Pública   → visible desde internet
IP Privada   → solo dentro de la red local
```

### Rangos privados comunes

```
10.0.0.0    – 10.255.255.255
172.16.0.0  – 172.31.255.255
192.168.0.0 – 192.168.255.255
```

---

## 🌍 DNS — Domain Name System

Traduce nombres de dominio legibles por humanos a direcciones IP.

```
google.com  →  142.250.64.110
```

### Flujo de resolución DNS

```
Usuario escribe URL
       ↓
   Caché local
       ↓
  Servidor DNS
       ↓
  Dirección IP
       ↓
  Carga el sitio
```

### Servidores DNS públicos comunes

| Proveedor | DNS primario | DNS secundario |
|-----------|-------------|----------------|
| Google | `8.8.8.8` | `8.8.4.4` |
| Cloudflare | `1.1.1.1` | `1.0.0.1` |

```bash
# Limpiar caché DNS en Windows
ipconfig /flushdns

# Consultar DNS en Linux
nslookup google.com
```

---

## 📡 DHCP — Dynamic Host Configuration Protocol

Asigna automáticamente una dirección IP a cada dispositivo que se conecta a la red.

### Flujo DORA

```
Dispositivo  →  DISCOVER  →  Servidor DHCP
Dispositivo  ←   OFFER    ←  Servidor DHCP
Dispositivo  →  REQUEST   →  Servidor DHCP
Dispositivo  ←    ACK     ←  Servidor DHCP
```

| Paso | Descripción |
|------|-------------|
| **Discover** | El dispositivo busca un servidor DHCP |
| **Offer** | El servidor ofrece una IP disponible |
| **Request** | El dispositivo acepta la IP ofrecida |
| **ACK** | El servidor confirma la asignación |

> Sin DHCP, cada dispositivo necesitaría una IP configurada manualmente.

---

## 🔌 Ports — Puertos

Canal lógico que permite identificar qué aplicación debe recibir el tráfico dentro de un dispositivo.

```
IP Address  →  identifica el dispositivo
Puerto      →  identifica la aplicación
```

### Puertos comunes

| Puerto | Protocolo | Uso |
|--------|-----------|-----|
| `22` | SSH | Conexión remota segura |
| `80` | HTTP | Navegación web |
| `443` | HTTPS | Navegación web segura |
| `3306` | MySQL | Base de datos |
| `53` | DNS | Resolución de nombres |
| `67/68` | DHCP | Asignación de IPs |

### Rangos de puertos

```
0    – 1023   → puertos bien conocidos (reservados)
1024 – 49151  → puertos registrados
49152 – 65535 → puertos dinámicos / privados
```

---

## ⚖️ TCP vs UDP

Ambos son protocolos de transporte, pero con comportamientos distintos.

| Característica | TCP | UDP |
|----------------|-----|-----|
| **Confiabilidad** | ✅ Garantiza entrega | ❌ Sin garantía |
| **Orden de paquetes** | ✅ Ordenado | ❌ Sin orden |
| **Velocidad** | Más lento | Más rápido |
| **Conexión** | Orientado a conexión | Sin conexión |
| **Uso típico** | Web, email, SSH | Streaming, DNS, juegos |

### TCP — Handshake de 3 pasos

```
Cliente  →   SYN    →  Servidor
Cliente  ← SYN-ACK  ←  Servidor
Cliente  →   ACK    →  Servidor
```

### ¿Cuándo usar cada uno?

```
TCP → cuando importa que los datos lleguen completos y en orden
UDP → cuando importa la velocidad y se tolera pérdida de datos
```

---

## 🔎 Conceptos para Investigar

- [ ] Qué es una **subred** y cómo se calcula la máscara
- [ ] Diferencia entre **IP estática y dinámica**
- [ ] Cómo funciona **NAT** (Network Address Translation)
- [ ] Qué es **ICMP** y cómo lo usa el comando `ping`
- [ ] Modelo **OSI** y en qué capa opera cada protocolo