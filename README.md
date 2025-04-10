# sharanihin2
УСТАНОВКА ПАКЕТА WGET
Попытка установки wget:

Вы пытаетесь установить пакет wget с помощью команды    

      sudo yum install wget

Появляется ошибка: is not in the sudoers file. Это означает, что у вашего пользователя нет прав на выполнение команд с sudo.

![image](https://github.com/user-attachments/assets/2283e31e-f885-431b-ae98-a10e8cdc1731)

Решение проблемы с правами sudo:

Переходите под пользователем root с помощью команды su .

![image](https://github.com/user-attachments/assets/dc4bd70f-ba27-46cc-a0d8-c94425a5f453)

Открываете файл sudoers с помощью команды visudo.
Находите строку root ALL=(ALL) ALL и добавляете под ней строку для вашего пользователя:


Ее мы будем исправлять используя следующие команды
Заходим под root-ом при помощи команды:



Далее уже под рутом вводим команду 

     sudo visudo 

![image](https://github.com/user-attachments/assets/2c1d8512-1395-4bb4-8ffc-26895e2f1a06)

и мы попадаем в файл sudoers
там мы находим строку root  ALL=(ALL)  ALL
вместо root может быть другое название

![image](https://github.com/user-attachments/assets/9734017e-74ea-4c33-9aee-7a00b60f4072)
Строй ниже пишем 


(Ваще имя пользователя) без скобок)нажимаем TAB ALL=(ALL)TAB ALL
И должно получиться как указно на скриншоте

![image](https://github.com/user-attachments/assets/55c128f7-a26d-4578-bdb3-5da93e7004f9)

далее нам нужно сохранить и выйти из файла 

для этого мы нажимаем Esc у нас появляет двоеточие, далее Shift+ж потом wq!

# Для чего эти махинации

 Кнопка | Обозначение |
 |-------------|-------------|
 |Esc   | Эта клавиша используется для перехода в командный режим из режима вставки. В командном режиме вы можете выполнять команды, такие как сохранение или выход   |
 |Появление двоеточия (:)|После нажатия Esc вы вводите двоеточие, чтобы начать ввод команды в командной строке vi/vim |
 |w|write (сохранить) — сохраняет изменения в файле|
 |q|quit (выйти) — выходит из редактора|
 |!|Этот символ используется для принудительного выполнения команды|
 

![image](https://github.com/user-attachments/assets/3c95212e-b59e-47cd-a77e-97b37962347e)

После успешного сохранения файла мы попадаем в нашу командную строку
и нам надо снова написать команду sudo yum install wget

![image](https://github.com/user-attachments/assets/7dbfa7ae-1b8f-406d-aecf-49b7f978f1bb)

если все сделали правильно у нас начнется загрузка

![image](https://github.com/user-attachments/assets/33fe084e-d4b5-4111-8827-2dbdb5c01a65)

все установилось успешно переходим к слудующему шагу 
устанавливаем curl при помощи команды sudo yum install curl

![image](https://github.com/user-attachments/assets/e1c0c8af-0511-4ac6-9783-ab94d6cb102f)

![image](https://github.com/user-attachments/assets/504211fc-4f24-4153-aea5-d08d7288464d)

Далее делаем репозиторий при помощи команты (sudo wget -P /etc/yum.repos.d/ https://download.docker.com/linux/centos/docker-ce.repo) 

При помощи клавишь Ctrl+Shift+v код можно скопировать и вставить в виртуальной машине

![image](https://github.com/user-attachments/assets/7c0c81e5-4e54-4e11-8e8d-17de281c098a)

После успешного внедрения репозитория, нам нужно установить docker при помощи команды sudo yum install docker-ce docker-ce-cli containerd.io

![image](https://github.com/user-attachments/assets/9655f0aa-3de2-4717-b260-8eb695a68251)

вводим пароль и начинается установка докера

![image](https://github.com/user-attachments/assets/f3d4586d-6d92-4526-986e-27f43776a9a4)

при запросе "Is this ok" пишем букву "у" и нажимаем Enter

![image](https://github.com/user-attachments/assets/4e9f6b69-fd85-4f1f-82c3-9de0aecb7cb3)

После успеной установки запускаем докер и разрешаем автозапуск командой "sudo systemctl enable docker --now"

![image](https://github.com/user-attachments/assets/d016a172-c1cf-4ab2-a3a3-bc071c211d5f)

Устанавливаем переменную "COMVER=$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep 'tag_name' | cut -d\" -f4)" 

![image](https://github.com/user-attachments/assets/a5c4ac42-4a9a-4607-97c4-3d12c32c104f)

Выкачиваем последний докер компост командой sudo curl -L "https://github.com/docker/compose/releases/download/$COMVER/docker-
compose-$(uname -s)-$(uname -m)" -o /usr/bin/docker-compose

![image](https://github.com/user-attachments/assets/bf5ed307-6191-46da-8c21-3598b32e71b4)

Далее нам нужно дать права. Права мы дадим командой sudo chmod +x /usr/bin/docker-compose

![image](https://github.com/user-attachments/assets/8e67f702-5ba6-4c9b-b0a8-fb4c59838474)

Ставим последнюю версию докер компоса командой docker-compose --version

![image](https://github.com/user-attachments/assets/c1e63bc8-7391-44ef-9f76-49d799ee8f94)

Устанавливаем git командой sudo yum install git

![image](https://github.com/user-attachments/assets/f863e032-eed7-4008-8c1c-109cfd7b14b7)

Далее выкачиваем командой git clone https://github.com/skl256/grafana_stack_for_docker.git

![image](https://github.com/user-attachments/assets/e78186f8-eeb4-4525-8eee-9bd8ad4f3fb2)

Переходим в графану cd grafana_stack_for_docker

![image](https://github.com/user-attachments/assets/bca5fdbb-8120-4a6f-b363-a32eb07638eb)

Дальше создаем там папки sudo mkdir -p /mnt/common_volume/grafana/{grafana-config,grafana-data,prometheus-data}

![image](https://github.com/user-attachments/assets/0886eeb1-d624-45b7-886d-3f65a0169c6e)

Дальше нам нужно дать права, это мы делаем командой sudo chown -R $(id -u):$(id -g) {/mnt/common_volume/swarm/grafana/config,/mnt/common_volume/grafana}

![image](https://github.com/user-attachments/assets/4626d377-89e5-4f7f-b566-c91365dcb46c)

команда touch /mnt/common_volume/grafana/grafana-config/grafana.ini

![image](https://github.com/user-attachments/assets/8d37a183-b80f-461d-98dc-2c8755cc5b92)

Копируем все файлы из директории config/ в директорию /mnt/common_volume/swarm/grafana/config/. при помоши команды 
"cp config/* /mnt/common_volume/swarm/grafana/config/"

![image](https://github.com/user-attachments/assets/9317698f-0546-4c48-b3f2-738872fe2a47)

перезапысываем существующий файл grafana.yaml в файл docker-compose.yaml командой             "mv grafana.yaml docker-compose.yaml"

запускаем       sudo docker compose up -d

![image](https://github.com/user-attachments/assets/30a2fa7d-1d94-4e90-855d-103127887e88)

Открываем браузер и в поиске пишем              
      
      localhost:3000

      успешный запуск 

тут у меня уже введен логин и пароль, но при первом входе потребует логин и пароль

![image](https://github.com/user-attachments/assets/15f34c73-8b94-4dc1-9e9c-766ac5bca9b9)

Для перехода в конфигурационный файл докера можно с помощью команды 
      
      vi docker-compose.yaml

для выхода пишем

      :wq

      

![image](https://github.com/user-attachments/assets/2cb2f0ad-67ce-4454-bed3-c60cd493193b)

Запускаем sudo docker compose up -d

![image](https://github.com/user-attachments/assets/4e202152-62b4-4e60-aa5b-33fa00d8a23c)

Пишем команду 

      sudo docker compose stop

Команда "stop" используется для остановки всех контейнеров, определённых в файле docker-compose.yml, который находится в текущей директории. 

![image](https://github.com/user-attachments/assets/9f476a9b-3aa5-4050-8844-25adf5afeb2c)

Чтобы продолжить дальше выполнять команды нужно снова запустить 
           
            sudo docker compose up -d

![image](https://github.com/user-attachments/assets/264b1c9f-e982-40f5-9382-b98833c08392)

Дальше команда используется для остановки и удаления контейнеров. 
      
      sudo docker compose down

![image](https://github.com/user-attachments/assets/0e0291fc-ff0a-40cd-a2e9-c898206b47fa)

Снова запускаем 

![image](https://github.com/user-attachments/assets/0d9f09cc-cd3d-470b-90bf-ab9cb02bb130)

Команда отображает информацию о контейнерах, определенных в вашем файле docker-compose.yml, включая их статус

      sudo docker compose ps

![image](https://github.com/user-attachments/assets/ae46239a-aad9-4736-ae21-af99505c791f)

#Прометей

копирую конфигурационные файлы с github командой

      sudo git clone https://github.com/SharanihinMaksim/sharanihin2.git

![image](https://github.com/user-attachments/assets/90140b9a-f824-4553-888b-e26868ce6e13)

проверяем что репозиторий успешно установлен

      ls

![image](https://github.com/user-attachments/assets/9d53aed5-a268-473d-b426-7a1b3fa54b91)

копируем конфигурационный файл докера в папку с Grafan

      cp docker-compose.yaml /home/fedor/grafana_stack_for_docker/

![image](https://github.com/user-attachments/assets/0453a37c-68c4-43db-ad2e-1941caff51b4)

Тоже самое проделываем prometheus

      cp prometeus.yaml /home/fedor/grafana_stack_for_docker/

![image](https://github.com/user-attachments/assets/f08387c5-44f6-41aa-b170-370ea09dcc33)

переименовываем файл конфигурации с prometeus.yaml на prometheus.yaml (если в его названии была ошибка)

используя команду       
      
      mv prometeus.yaml prometheus.yaml

переносим конфигурационный файл prometheus.yaml в конфиг Grafana

используя команду 

      mv prometheus.yaml /mnt/common_volume/swarm/grafana/config

![image](https://github.com/user-attachments/assets/3eee9b7f-dd65-4da0-9bcf-231d467f04df)

Проверяем наличие 
      
      ls

![image](https://github.com/user-attachments/assets/4bc9820e-9303-424a-a4ab-ae851fb45efd)

запускаем docker compose в фоновом режиме

используя команду 
            
      sudo docker compose up -d

![image](https://github.com/user-attachments/assets/22001310-4335-4031-9779-521ffe2d7679)

переходим на сайт localhost:3000

-Пользователь и Пароль GRAFANA: admin
-Код графаны: 3000
-Код прометеуса: http://prometheus:9090

# В меню выбираем вкладку Dashboards и создаем Dashboard

![image](https://github.com/user-attachments/assets/a545de41-d71c-40a2-b199-4f814e00bc07)

Заполняем данные в открывшемся окне

# Пункт Connection

  -http://prometheus:9090
  -Пункт Authentication

# Базовая аутентификация
  -Пользователь: admin
  -Пароль: admin

#Нажимаем на Save & test и должно показывать зелёную галочку

в меню выбираем вкладку Dashboards и создаем Dashboard

#жмем кнопку "Import dashboard"

нажимаем кнопку +Добавить визуализацию, а затем «Настроить новый источник данных»

выбираем Prometheus

В пункт Find and import dashboards for common applications at grafana.com/dashboards:

вписываем 1860

![image](https://github.com/user-attachments/assets/7f1a547c-1b86-4c57-9f9e-bc070cb97af8)




