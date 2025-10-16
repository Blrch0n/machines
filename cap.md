# Бие даалт – Тайлан

## Machine 01 — <Cap, IP:10.10.10.245>

![Openvpn](images/m01/photo1.png)

## Энэ бүх даалгаваруудыг хийхээс өмнө target machine тай нэг сүлжээнд орох шаардлагатай.Тиймээс openvpn ашиглана нэг сүлжээнд байгаа юм шиг болгосон.

### 1) How many TCP ports are open? Hint:Scan the host with nmap.

![Nmap](images/m01/photo2.png)

    3

### 2) After running a "Security Snapshot", the browser is redirected to a path of the format /[something]/[id], where [id] represents the id number of the scan. What is the [something]?

![Website](images/m01/photo3.png)

    data

### 3) Are you able to get to other users' scans?

![Website](images/m01/photo4.png)

![fuff](images/m01/photo5.png)

    yes

### 4) What is the ID of the PCAP file that contains sensative data?

![Website](images/m01/photo6.png)

![WireShark](images/m01/photo7.png)

    0

### 5) Which application layer protocol in the pcap file can the sensetive data be found in?

![WireShark](images/m01/photo7.png)

    ftp

### 6) We've managed to collect nathan's FTP password. On what other service does this password work?

![Nmap](images/m01/photo2.png)

    ssh

### 7) Submit the flag located in the nathan user's home directory.

![ssh](images/m01/photo8.png)

    32267627d86088eb79f58dfb5d211b9d

### 8) What is the full path to the binary on this machine has special capabilities that can be abused to obtain root privileges?

![getcap](images/m01/photo9.png)

    /usr/bin/python3.8

### 9)Submit the flag located in root's home directory.

![python3.8](images/m01/photo10.png)
![root flag](images/m01/photo11.png)

    bbf65451187ab61533044698c36821fd
