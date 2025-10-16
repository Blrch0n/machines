# Бие даалт – Тайлан

## Machine 05 — <Code, IP:10.10.11.23>

### 1) Nmap

![alt text](image-56.png)

### 2.) execute commands in sandbox

![alt text](image-57.png)

### 3.) found out.

![alt text](image-58.png)

### 4.) Python “Code Editor” sandbox: хориглосон түлхүүр үгийг bypass хийсэн.

![alt text](image-59.png)

### 5.) Гүйцэтгэлийг батлах: nc руу дамжуулсан

![alt text](image-61.png)

### 6.) reverse shell хийж холболт үүсгэв.

![alt text](image-60.png)

![alt text](image-62.png)

### 7.) Listening

![alt text](image-63.png)

### 8.) user flag.txt

![alt text](image-64.png)

### 9.) SQLite: аппын хэрэглэгч, hash-уудыг харсан.

![alt text](image-65.png)

### 10.) Crack

![alt text](image-66.png)

### 11.) Жинхэнэ хэрэглэгч рүү үсэрсэн

![alt text](image-67.png)

### 12.) скриптээр root хүрэх шанс

![alt text](image-68.png)

### 13.) task.json харав

![alt text](image-69.png)

### 14.) backy.sh харав

![alt text](image-70.png)

### 15.) task.json-оо file аа өөрчиллөв.

![alt text](image-71.png)

### 16.) sudo /usr/bin/backy.sh ~/backups/task.json

![alt text](image-72.png)

### 17.) Бэлгийг задлах: root-ийн гэрийг авчээ

![alt text](image-73.png)

### 18.) ssh/id_rsa-г хуулж root.key болгосон

![alt text](image-75.png)

# Дүгнэлт

### Эхлэл: 22/SSH, 5000/Gunicorn дээр “Python Code ExXditor” ил.

### Foothold (RCE): Кодын редактор нь түлхүүр үгнүүдийг л хориглосон, харин Python-ийн object graph-аар (**subclasses** → **globals** → sys.modules → os.system) тойрч RCE авсан. Гаралтыг UI буцаадаггүй тул Netcat руу чиглүүлж гүйцэтгэлийг баталгаажуулсан, дараа нь /dev/tcp reverse shell авч app-production болгон ажиллуулсан.

### Итгэмжлэл задлалт: App-ын database.db (SQLite) доторх хэрэглэгчдийн unsalted MD5 hash-уудыг hashcat -m 0-оор задлаад development:development, martin:nafeelswordsmaster илэрсэн. Нууц үг дахин ашигласнаар martin руу SSH орсон.

### Эрх нэмэгдүүлэлт: sudo -l дээр NOPASSWD: /usr/bin/backy.sh илэрсэн

# Кибер халдлагыг сөрөн тэсвэрлэх зөвлөмж

# Веб апп ба sandbox хатууруулалт

### Жинхэнэ sandbox: Контейнерт (namespace, cgroup) тусгаарлаж, сүлжээний гаралт хориглох, read-only FS, noexec mount, seccomp/AppArmor профайл.

### Суудогийн эрх: NOPASSWD: backy.sh-ийг цуцлах
