# sharanihin2
Начинаем установку пакета wget с помощью команды sudo yum install wget
У нас появляется ошибка is not in the sudoers file

![image](https://github.com/user-attachments/assets/2283e31e-f885-431b-ae98-a10e8cdc1731)

Ее мы будем исправлять используя следующие команды
Заходим под root-ом при помощи команды:
![image](https://github.com/user-attachments/assets/dc4bd70f-ba27-46cc-a0d8-c94425a5f453)

Далее уже под рутом вводим команду 
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
![image](https://github.com/user-attachments/assets/7c0c81e5-4e54-4e11-8e8d-17de281c098a)
