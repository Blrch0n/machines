# Бие даалт – Тайлан

## Machine 05 — <Dog, IP:10.10.11.23>

### 1)

### Порт хайлт

### 22/ssh, 80/http илэрнэ. HTTP дээр Apache 2.4.41, Backdrop CMS баннер гарна.

![alt text](image-3.png)

### 2)

### .git ыг git dumper ашиглана brute force хийж clone хийсэн.

![alt text](image-4.png)

### 3)

### settings.php-оос DB credential авах

![alt text](image-5.png)

### 4)

![alt text](image-6.png)

### 5)

### Backdrop-ийн хэрэглэгчийг URL alias-аар олох

![alt text](image-7.png)

### Админ нэвтрэлт (нууц үг дахин ашиглалт)

![alt text](image-8.png)

### 6)

### Backdrop хувилбар тодорхойлох

![alt text](image-9.png)

### exploit file

![alt text](image-11.png)

### 7)

![alt text](image-10.png)

### 8)

### generate shell command file

![alt text](image-12.png)

### module upload ашиглаж foothold авах

![alt text](image-13.png)

### 9)

### shell агуулсан агуулсан файлаа сервер дээр ажиллуулах

![alt text](image-14.png)
![alt text](image-15.png)

### www-data user ээр хүссэн коммандаа хийж болохоор болгосон.

![alt text](image-16.png)

### 10)

### Reverse shell команд

![alt text](image-18.png)

### target machine ээс local machine рүү холбогдсон.

![alt text](image-19.png)

### 11)

### TTY сайжруулах

![alt text](image-20.png)

### Хэрэглэгч рүү үсрэх (нууц үг дахин ашиглалт)

![alt text](image-21.png)
![alt text](image-22.png)

![alt text](image-23.png)
![alt text](image-24.png)
![alt text](image-25.png)

### sudo bee ашиглаж root

![alt text](image-26.png)
![alt text](image-27.png)

### SUID bash хийх

![alt text](image-28.png)

# Дүгнэлт

### Нээлттэй мэдээлэл алдагдал: Вебийн рүүт дээр .git/ ил байсан нь репог бүхэлд нь татуулах боломж олгож, settings.php-оос MySQL нууц үг илэрсэн.

### Нууц үг дахин ашиглалт: DB-ийн нууц үгийг админ (tiffany) болон системийн хэрэглэгч (johncusack) хоёуланд нь давхар ашигласнаар админ панел ба дараа нь SSH нэвтрэлт авч чадсан.

### Foothold (RCE): Backdrop CMS-ийн админ модуль суулгах боломжийг ашиглан PHP reverse shell агуулсан архивыг байршуулж, www-data эрхтэй команд гүйцэтгэсэн.

### Privilege escalation: johncusack хэрэглэгч нь sudo /usr/local/bin/bee ажиллуулах эрхтэй байсан. bee --root=… eval "shell_exec('…')" ашиглан root дээр дурын систем команд гүйцэтгэж эцсийн эрх авч дууссан.

# Кибер халдлагыг сөрөн тэсвэрлэх зөвлөмж

### .git-ийг хэзээ ч вебээр үзэгдэхээр бүү үлдээ

### Апп-ын config/secret файлуудыг веб-руутээс гаргаж, зөвхөн апп-д унших эрхтэй болго:

### Шинэчилгээ: Backdrop-ийг хамгийн сүүлийн тогтвортой хувилбар руу байнга шинэчил
