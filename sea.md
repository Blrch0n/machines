# Бие даалт – Тайлан

## Machine 06 — <Sea, IP:10.10.11.23>

### 1)

### Target-ын онгорхой портыг олох болон ямар сервер, сервис дээр ажиллаж байгаа харах.

![alt text](image-29.png)

### 2)

![alt text](image-30.png)

### 3)

### Өмнөх зурагт үзүүлсэн форм дээр sql injection хийж болохгүй байсан учир directory brute force хийсэн

![alt text](image-31.png)
![alt text](image-32.png)

### 4)

![alt text](image-33.png)

### 5)

### brute force хийсэний үр дүнд тухай нь веб сайт дээр онгорхой байсан файлуудыг олж уншсан.

![alt text](image-34.png)
![alt text](image-35.png)

### 6)

### Манай exploit file. Энэхүү exploit нь admin click товч дарах үед xss.js server дээрээ ажиллуулж xss.js нь main.zip файлыг дуудна уг файл дотор reverse shell ын файл байгаа.

![alt text](image-36.png)
![alt text](image-37.png)

### 7)

### Exploit-оо ашиглаж байна.

![alt text](image-38.png)

### 8)

![alt text](image-39.png)

### 9)

### exploit үйлдлүүдийг харуулж байна.

![alt text](image-76.png)

### 10)

### www-data user-ээр remote хандалт хийсэн. Мөн үүний дараа bash аа ажиллуулсан.

![alt text](image-78.png)

### 11)

### database дотор bcrypt ээр hash лсан нууц үг байсан.

![alt text](image-79.png)

### 12)

### үүнийг hashcat ашиглан crack хийсэн.

![alt text](image-80.png)

### 13)

### crack-лсан нууц үгээ ашиглан amay user ээр орсон.Мөн netstat ашиглан локал дээрээ listen хийж байгаа tcp port уудаг харсан.

![alt text](image-81.png)

### 14)

### port forwarding хийсэн вэб сайтаа локал дээрээ ашигласан.

![alt text](image-87.png)

### 15)

![alt text](image-82.png)

### 16)

### analyse хийх үед post хийх хүсэлт явуулж тухайн комманд back end дээрээ ажилладаг гэдгийг олж мэдсэн.

![alt text](image-83.png)

### 17)

### Өмнөх зурган дээр байсан хүсэлтийг өөрчлөнө .Тухайн back end дээр нь өөрчлөлт хийж үзсэн.

![alt text](image-84.png)

### 18)

### Энэ сул талыг ашиглан target ын машинаас өөрлүүгээ reverse shell хийх оролдлого хийсэн.

![alt text](image-86.png)

### 19)

### body дотор байсан command амжилттай ажиллаж роот эрхээр тухайн target machine аас миний port руу амжилттай холболт хийгдсэн.

![alt text](image-85.png)

### Дүгнэлт

### Эх нэвтрэлт: WonderCMS 3.2.0 дээрх CVE-2023-41425 (Reflected XSS)-ийг ашиглаж, админы хөтөчөөс CSRF token авч “remote theme install”-аар PHP reverse shell суулгаж www-data эрхээр хостод орсон.

### Хажуу чиглэлт: /var/www/sea/data/database.js-оос bcrypt ($2y$) нууцлалтай админ нууц үгийг олж, hashcat -m 3200-оор mychemicalromance болгон задлаад su - amay хийж amay хэрэглэгчээр шилжсэн.

### Дотоод үйлчилгээ: Хост дээр 127.0.0.1:8080-д ажиллаж байсан “monitoring” вебийг ssh -L-ээр локал руу туннелдан нээж, log_file параметрт командын шахалт хийснээр root эрхтэй процессыг гүйцэтлүүлж root авсан.

### Гол сургамж: Хуучин CMS + админ XSS + модуль суулгалт = RCE. Нууц үгийн дахин ашиглалт системийн хэрэглэгч рүү үсрэхэд тусалсан. Root-аар ажилладаг, shell-д суурилсан кодтой дотоод хэрэгсэл шууд командын шахалт болж хувирсан

### Кибер халдлагыг сөрөн тэсвэрлэх зөвлөмж

### WonderCMS-ийг хамгийн сүүлийн хувилбарт шинэчил; дурын URL-аас модуль/теэм суулгахыг хориглох эсвэл зөвхөн итгэмжлэгдсэн репо руу хязгаарлах

### Апп ба системийн нууц үгийг давхардаа бүү ашигла

### админ бүрт 2FA боломжтой бол идэвхжүүлэх
