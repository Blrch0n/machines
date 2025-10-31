# Бие даалт – Тайлан

## Machine 16 — <Knife, IP:10.10.11.38>

### 1.) nmap-аар зорилтотыг скан хийхэд 2 нээлттэй порт байгааг харуулав.

![alt text](image.png)

### 2.) Вэб enum (Фолдер хайлт:)

![alt text](image-1.png)

### 3.) Header шалгах:

![alt text](image-2.png)

### 4.)

![alt text](image-3.png)

### 5.)

![alt text](image-4.png)

### 6.) Header шалгах:

![alt text](image-5.png)
![alt text](image-6.png)

### 7.) Reverse shell

![alt text](image-7.png)

### 8.) target machine интернетгүй байсан тул локалаар linepear ээр дамжуулсан.

![alt text](image-13.png)

### linstening хийсэн

![alt text](image-8.png)

### 9.) linPEAS бол Linux машин дээр эрх өсгөх (priv-esc) боломжуудыг автоматаар самнаж олж өгөх all-in-one скрипт.

![alt text](image-9.png)

### 10.) Vim ашигласан

![alt text](image-10.png)

### 11.) Дараа нь bash болгож

![alt text](image-11.png)

### 13.) Үүний дагуу рүүт эрхтэй болсон.

![alt text](image-12.png)

# Дүгнэлт

### Энэ машин дээрх нэвтрэлтийн үндсэн шалтгаан нь PHP 8.1.0-dev-ийн суурилуулсан backdoor (эрх мэдэлгүйгээр User-Agentt: zerodium... толгойгоор алсаас команд ажиллах) байв. Вэб сервер(HTTP)-ээс довтлогч реверс shell авч, james хэрэглэгчийн эрхээр системд орсон.

### Дараагийн шатанд sudoers буруу тохиргоо (james нь sudo /usr/bin/knife-ийг NOPASSWD-аар ажиллуулж чаддаг) ашиглагдаж, knife exec-ээр root руу шууд үсрэх боломж олгосон.

# Кибер тэсвэртэй байдлын зөвлөмж

## Эрхийн загвар (sudoers/least privilege)

### NOPASSWD арилгах: james-ын sudo /usr/bin/knife эрхийг устгах эсвэл зөвхөн аюулгүй, хязгаарлагдмал параметртэй wrapper скрипт рүү заах.
