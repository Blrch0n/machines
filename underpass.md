# Бие даалт – Тайлан

## Machine 06 — <Underpass, IP:10.10.11.23>

# 1.)

### UDP суваг ил задгай: TCP-д зөвхөн 22/80 харагдсан ч UDP скан хийснээр SNMP (161/udp) болон RADIUS (1812/1813/udp) ил гарсныг тогтоосон. SNMP-ийн нийтийн community public-аар уншиж болохоор байснаар системийн нэр, байрлал, админ холбоо, “daloradius ажиллаж байна” гэсэн мессеж зэрэг мэдрэмтгий мэдээлэл ил болов.

![alt text](image-41.png)

# 2.)

![alt text](image-42.png)

# 3.) SNMP check ашиглан hostname, kernel, contact, location, server ын нэрийг олж мэдсэн.

![alt text](image-43.png)

# 4.)

![alt text](image-44.png)

# 5.) daloRADIUS зам: 403

![alt text](image-46.png)

# 6.) Operators default login url

![alt text](image-45.png)

# 7.) Default credential-оор нэвтэрсэн

![alt text](image-47.png)

![alt text](image-48.png)

# 8.) Hash Password found

![alt text](image-49.png)

# 9.) Хэрэглэгчийн hash авч crack хийсэн

![alt text](image-50.png)

# 10.) SSH foothold авсан

![alt text](image-51.png)

# 11.) sudo -l. mosh server

![alt text](image-88.png)

# 12.) exploring

![alt text](image-52.png)

# 13.) mosh-server асааж, түлхүүрийг нь авсан.mosh-client-ээр root-рүү холбогдсон

![alt text](image-55.png)

# 14.) root user ээр орж flag аа олсон.

![alt text](image-54.png)

# Дүгнэлт

### Эхлэл (Enumeration): TCP дээр 22/80 нээлттэй, Apache “It works” default хуудас. UDP сканаар SNMP (161/udp), RADIUS (1812/1813/udp) илэрсэн.

### Итгэмжлэл задлалт: Operators хэсгээс svcMosh хэрэглэгчийн unsalted MD5 hash авч, john --format=Raw-MD5-аар underwaterfriends болгон задлаад SSH-ээр хэрэглэгчийн түвшний foothold авсан

### Эрхийн өсгөлт: sudo -l дээр NOPASSWD: /usr/bin/mosh-server тохируулга байснаар mosh-server-ийг root-оор асааж, хэвлэсэн MOSH CONNECT <порт> <түлхүүр>-ийг ашиглан MOSH_KEY=<түлхүүр> mosh-client <ip> <порт>-оор холбогдож root эрхтэй session авсан

### Шалтгааны гол зангилаа: SNMP буруу тохиргоо (v1/public), daloRADIUS-ын анхдагч эрх өөрчлөөгүй, сул hash алгоритм (unsalted MD5), SSH дээр password login нээлттэй, мөн sudo-гийн NOPASSWD-тай буруу эрх олголт.

# Кибер халдлагыг сөрөн тэсвэрлэх зөвлөмж

### SNMP firewall асаах: v1/v2c-г идэвхгүй болгоод SNMPv3 (auth+priv) ашиглах. Менежментийн IP-гаар л нэвтрүүлэх ACL тавих. Хэрэггүй бол бүрмөсөн хаа.

### Mosh UDP range (60000–61000)-г by-default хаах. Зайлшгүй хэрэгтэй бол зөвшөөрөл, логтойгоор нээ.

### Давтан ашиглалт-ыг хориглох бодлого (PAM pam_pwquality, pam_pwhistory), тогтмол эргэлт/солих.

### SSH-д түлхүүрээр нэвтрэх; password login-ийг хаах.
