# liza
Сначала мы ввели `код sudo yum install wget`, с помощью этой команды мы получаем ошибку "is not in the sudoers file" чтобы исправить ошибку вводим команду `su root`, далее вводим пароль администратора 
![image](https://github.com/user-attachments/assets/087ce2c4-157a-426f-a8fa-4819b58582c6)

Теперь мы вводим команду `vi /ets/sudoers` открыли конфигурационный файл. Листаем до строки "root", меняем эту строку на имя пользователя `tee ALL=(ALL)       ALL`
![image](https://github.com/user-attachments/assets/833dee0b-0bdd-4eb7-bc38-c3c973521fe1)

Далее нажимаем на комбинацию клавиш Shift + ж и у нас появляется строка с ":". Туда вводим `wq!` чтобы сохранить прогресс, а после если зашли в конфигурационный файл чтобы выйти вводим `q!`

![image](https://github.com/user-attachments/assets/a6cc1a3e-79da-443c-a38f-d90a67a7cfd7)
![image](https://github.com/user-attachments/assets/ce7bb00c-e2aa-4af0-9598-2b3e1c96cd9a)

После выхода из конфигурационный файла вводим команду `sudo yum install wget`, вводим пароль администратора, все это для установки утилита wget

![image](https://github.com/user-attachments/assets/35498f5c-92e3-4a15-bb71-1196d9d05caa)


                                                                                                    08.02.2025
Первым делом мы вводим команду `sudo wget -P /etc/yum.repos.d/ https://download.docker.com/linux/centos/docker-ce.repo` - эта команда загружает файл репозитория Docker и сохраняет его в директории, где YUM может его использовать для установки и обновления пакетов Docker.

![image](https://github.com/user-attachments/assets/267e8c02-ff29-440b-8d80-8c490a9aa509)


Потом вводим команду `sudo yum install docker-ce docker-ce-cli containerd.io` - устанавливает необходимые пакеты для работы с Docker.

![image](https://github.com/user-attachments/assets/6cc081dd-0be2-4c39-8ece-2d9c1482f38a)
![image](https://github.com/user-attachments/assets/88d88688-1bc4-41dc-a94e-409d3f0762ab)

`sudo systemctl enable docker --now` - включает службу Docker для автоматического запуска. 

![image](https://github.com/user-attachments/assets/336c0a72-40df-4aaf-b3f0-be138cd7fb0b)



                                                                                              15.02.2025
Первоночально вводим команду `COMVER=$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep 'tag_name' | cut -d\" -f4)` она используется для получения номера последней версии Docker 
Следом пишим команду `sudo curl -L "https://github.com/docker/compose/releases/download/$COMVER/docker-compose-$(uname -s)-$(uname -m)" -o /usr/bin/docker-compose ` эта команда загружает исполняемый файл Docker Compose с GitHub и устанавливает его в систему
"sudo chmod +x /usr/bin/docker-compose"после выполнения этой команды вы сможете запускать Docker Compose из терминала, просто вводя команду "docker-compose"
Эту команду `docker-compose --version `вводим для тогда чтобы узнать версию docker

![image](https://github.com/user-attachments/assets/e1ff69db-fb72-4d93-88e0-234fc56b9395)

эта команда `sudo yum install git` для установки системы Git

![image](https://github.com/user-attachments/assets/3f057d30-f6f3-4e65-b420-f61fd52e6f9f)
![image](https://github.com/user-attachments/assets/0c2a759d-edb8-43ae-8b74-a43befe0320f)
![image](https://github.com/user-attachments/assets/f7bd0cb2-8b44-4e31-9aa7-dc6324721d09)


После устоновки мы пишим команду `git clone https://github.com/skl256/grafana_stack_for_docker.git`

![image](https://github.com/user-attachments/assets/3fb73322-dda5-4a23-aa09-dadd40df5310)


далее пишим команды:
`cd grafana_stack_for_docker` - эта команда перемещает вас в каталог

`sudo mkdir -p /mnt/common_volume/swarm/grafana/config` - эта команда создает каталог 

`sudo mkdir -p /mnt/common_volume/grafana/{grafana-config,grafana-data,prometheus-data}` - создание директорий для Grafana

`sudo chown -R $(id -u):$(id -g) {/mnt/common_volume/swarm/grafana/config,/mnt/common_volume/grafana}` - изменение владельца директорий

`touch /mnt/common_volume/grafana/grafana-config/grafana.ini` - создание файла конфигурации

`cp config/* /mnt/common_volume/swarm/grafana/config/` - копирование конфигурационных файлов

![image](https://github.com/user-attachments/assets/5260a30e-5cbd-44f0-8102-ab682eca2e7c)
![image](https://github.com/user-attachments/assets/4449081b-6a3e-44d0-b97a-d7622e883d41)

ДОЛГ
Команда `mv grafana.yaml docker-compose.yaml` - открыла файл docker-compose.yaml в текстовом редакторе vi.
Чтобы добавить изменение в текстовом редакторе нужно нажать кнопку insert.
В текстовом редакторе после services пишем node-exporter. Что бы сохранить изменения нужно нажать Esc и написать :wq!
![image](https://github.com/user-attachments/assets/234714b2-163a-4301-b9d2-0a666eb021e3)

![image](https://github.com/user-attachments/assets/6fb6e001-eead-4740-814c-fc8b71382b76)


![image](https://github.com/user-attachments/assets/7b30130c-e4f3-43db-a710-133aa0db4f59)

![image](https://github.com/user-attachments/assets/1a90284b-7682-41cf-a6c8-90ed3469e2f5)

![image](https://github.com/user-attachments/assets/f223feb6-c57f-4eb5-a7ff-7b0619323eae)

![image](https://github.com/user-attachments/assets/ab7fcae9-11c3-4c10-b5a9-a2f8fe896c17)

![image](https://github.com/user-attachments/assets/a37da795-356e-40ab-8232-ae1dc893777e)
