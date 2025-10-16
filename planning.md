# Бие даалт – Тайлан

## Machine 02 — <Planning, IP:10.10.11.68>

![Openvpn](images/m01/photo1.png)

## Энэ бүх даалгаваруудыг хийхээс өмнө target machine тай нэг сүлжээнд орох шаардлагатай.Тиймээс openvpn ашиглана нэг сүлжээнд байгаа юм шиг болгосон.

### 1) How many open TCP ports are listening on Planning?

![Nmap](images/m02/photo1.png)

    2

### 2) What subdomain of planning.htb hosts a data visualization monitoring platform?

![Website](images/m02/photo2.png)

    grafana.planning.htb

### 3) What version of Grafana is running on Planning?

![Website](images/m02/photo3.png)

![fuff](images/m02/photo4.png)

    11.0.0

### 4) What password can be found in the docker container environment variables?

![Website](images/m02/photo5_1.png)

![Website](images/m02/photo5.png)

![WireShark](images/m02/photo6.png)

    RioTecRANDEntANT!

### 5) Submit the flag located in enzo's home directory.

![WireShark](images/m02/photo7.png)

    963c319c543e5ed8858ffab59dad8515

### 6) Which port on Planning is running another web application locally?

![Nmap](images/m02/photo8.png)

    8000

### 7) What is the full path of the database file for the web application?

![ssh](images/m02/photo9.png)
![alt text](images/m02/image.png)

![ssh](images/m02/photo10.png)

    /opt/crontabs/crontab.db

### 8) What is the name of the web application running on port 8000?

![getcap](images/m02/photo11.png)

    Crontab UI

### 9)Submit the flag located in root's home directory.

![python3.8](images/m02/photo12.png)
![root flag](images/m02/photo13.png)

    Submit the flag located in the root user's home directory.
