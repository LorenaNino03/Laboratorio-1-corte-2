# Laboratorio-1-corte-2

La practica se realiza con virtualbox, se descarga maquina virtual de Kali Linux y Metasploitable 2
<img width="1054" height="514" alt="image" src="https://github.com/user-attachments/assets/a7a3e350-13ca-4afd-9e10-0ba1c206428a" />

Se procede a verificar la IP de la victima en Metasploitable con el comando IFCONFIG, en la parte inet addr, aparece dicha IP.
<img width="773" height="493" alt="image" src="https://github.com/user-attachments/assets/540eb9c5-d42b-49e3-bd76-3c0d377f55ef" />

# Entendiendo los Tipos de Red en VMware
# Bridged (Puente)
<img width="1007" height="400" alt="image" src="https://github.com/user-attachments/assets/0eb58440-780e-43a6-8430-7f96c463cfd5" />
Se pone maquina virtual en puente y la otra en NAT, se observa comunicación.
<img width="1826" height="923" alt="Captura de pantalla 2026-04-24 122110" src="https://github.com/user-attachments/assets/cde6c1d8-ff85-49f5-9bbf-097121bf7dd5" />
# NAT (Network Address Translation):
<img width="995" height="444" alt="image" src="https://github.com/user-attachments/assets/64354a93-fb83-4b95-8f65-9b1e413419bf" />
# Host-only (Solo Anfitrión): 
Se pone las maquinas solo anfitrión
<img width="697" height="311" alt="image" src="https://github.com/user-attachments/assets/0735f2e9-59cc-4cf8-be36-4141e72f2716" />
<img width="1033" height="431" alt="image" src="https://github.com/user-attachments/assets/1ab1bf9a-16b9-4ab0-a01b-712c46788062" />
Se valida la IP en ambas maquinas 
<img width="1410" height="657" alt="image" src="https://github.com/user-attachments/assets/8b230ba0-b2a8-4b00-bc1f-c487cc1c561b" />

# 6.2 Reconocimiento y Escaneo de Vulnerabilidades con Nmap
Escaneo de la Red con Nmap, con el comando nmap -sn 192.168.X.0/24 para mirar la subred para hosts activos
<img width="1195" height="335" alt="image" src="https://github.com/user-attachments/assets/feec86b2-cba9-4904-aa36-cda78e19f99e" />
# netdiscover es una excelente herramienta para el descubrimiento de hosts en redes locales (puede requerir sudo):
Podemos observar los host que estan conectados. 
<img width="1077" height="311" alt="image" src="https://github.com/user attachments/assets/d806d093-5cdf-4363-bdf6-82c99ad919a0" />

Identifique la IP de Metasploitable 2. Para el resto de la práctica.
<img width="732" height="113" alt="image" src="https://github.com/user-attachments/assets/3822d5eb-76ed-4967-b6ff-54efe0a3ca52" />

# 6.2.2 Escaneo Detallado de Puertos y Servicios con Nmap 
Se procede a realizar el escaneo de la vistima para verificar los puertos 
# Desglose de los flags de Nmap:
<img width="856" height="360" alt="image" src="https://github.com/user-attachments/assets/401880c1-c0fb-4797-83d2-60c6caa57356" />












