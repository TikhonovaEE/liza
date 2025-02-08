# liza
Сначала мы ввели код "sudo yum install wget", с помощью этой команды мы получаем ошибку "is not in the sudoers file" чтобы исправить ошибку вводим команду "su root", далее вводим пароль администратора 
![image](https://github.com/user-attachments/assets/087ce2c4-157a-426f-a8fa-4819b58582c6)

Теперь мы вводим команду "vi /ets/sudoers" открыли конфигурационный файл. Листаем до строки "root", меняем эту строку на имя пользователя "tee ALL=(ALL)       ALL"
![image](https://github.com/user-attachments/assets/833dee0b-0bdd-4eb7-bc38-c3c973521fe1)

Далее нажимаем на комбинацию клавиш Shift + ж и у нас появляется строка с ":". Туда вводим wq! чтобы сохранить прогресс, а после если зашли в конфигурационный файл чтобы выйти вводим q!

![image](https://github.com/user-attachments/assets/a6cc1a3e-79da-443c-a38f-d90a67a7cfd7)
![image](https://github.com/user-attachments/assets/ce7bb00c-e2aa-4af0-9598-2b3e1c96cd9a)

После выхода из конфигурационный файла вводим команду "sudo yum install wget", вводим пароль администратора, все это для установки утилита wget

![image](https://github.com/user-attachments/assets/35498f5c-92e3-4a15-bb71-1196d9d05caa)


08.02.2025
Первым делом мы вводим команду "sudo wget -P /etc/yum.repos.d/ https://download.docker.com/linux/centos/docker-ce.repo" - эта команда загружает файл репозитория Docker и сохраняет его в директории, где YUM может его использовать для установки и обновления пакетов Docker.

![image](https://github.com/user-attachments/assets/267e8c02-ff29-440b-8d80-8c490a9aa509)


Потом вводим команду "sudo yum install docker-ce docker-ce-cli containerd.io" - устанавливает необходимые пакеты для работы с Docker.

![image](https://github.com/user-attachments/assets/6cc081dd-0be2-4c39-8ece-2d9c1482f38a)
![image](https://github.com/user-attachments/assets/88d88688-1bc4-41dc-a94e-409d3f0762ab)

"sudo systemctl enable docker --now" - включает службу Docker для автоматического запуска. 

![image](https://github.com/user-attachments/assets/336c0a72-40df-4aaf-b3f0-be138cd7fb0b)
