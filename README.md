# Настройка рабочего окружения

<details>
<summary>Windows</summary>

### Установка VS Code

1. Заходим на оф.сайт https://code.visualstudio.com/ и нажимаем кнопку Download for Windows

<div align="center">
    <img src="assets/Рисунок1.png">
</div>

2.  Запускаем инсталятор и выбираем путь и параметры, дожидаемся конца установки

<div align="center">
    <img src="assets/Рисунок2.png">
</div>

3. Запускаем VS Code (VS Code предложит установить языковой пакет, соглашаемся если нужно, перезапустится)

### Установка Node.js

1. Идем на официальный сайт https://nodejs.org/en/ и качаем LTS версию
2. Запускаем инсталятор
3. Устанавливаем не меняя параметры кроме пути установки
4. Перезапускаем VS Code, открываем терминал и проверяем версию командой node -v

<div align="center">
    <img src="assets/Рисунок3.png">
</div>
Должно получиться так, только с номером вашей LTS версии.

### Установка git bash

1. Идем на оф.сайт https://git-scm.com/download/win и качаем Standalone Installer нужной разрядности
2. Запускаем инсталятор и следуем инструкциям на скриншотах
<div align="center">
    <img src="assets/Рисунок4.png">
    <img src="assets/Рисунок5.png">
    <img src="assets/Рисунок6.png">
    <img src="assets/Рисунок7.png">
    <img src="assets/Рисунок8.png">
    <img src="assets/Рисунок9.png">
    <img src="assets/Рисунок10.png">
    <img src="assets/Рисунок11.png">
    <img src="assets/Рисунок12.png">
    <img src="assets/Рисунок13.png">
    <img src="assets/Рисунок14.png">
</div>

### Настройка Git bash

1. В любой папке, нажатием правой кнопки мыши, вызываем контекстное меню и 
выбираем пункт `Git Bash Here`
2. В открывшемся терминале необходимо ввести две команды
`$ git config --global user.name "Ваш никнейм на github"`
`$ git config --global user.email ВашEmailНаGithub@example.com`
3. Проверяем коммандой `git config --list`

### Генерация ключа  SSH

1. Открываем командную строку Windows
2. Вводим команду `ssh-keygen`
3. Приложение запросит место сохранения, предлагая по умолчанию, нажимаем Enter
`C:\users\имя_пользователя\.ssh\id_rsa`
4. Далее вам будет предложено ввести кодовую фразу. Нажмите клавишу Enter, чтобы пропустить
5. Подтверждение кодовой фразы так-же пропускаем
6. После генерации идем по пути `C:\users\имя_пользователя\.ssh\` и открываем файл `id_rsa.pub` любым текстовым редактором и копируем содержимое.
7. Идем в настройки аккаунта на GitHub

<div align="center">
    <img src="assets/Рисунок15.png" width="200">
</div>

8. Нажимаем кнопку New SSH Key и в открывшемся окне вставляем содержимое из файла `id_rsa.pub` и вводим название ключа

<div align="center">
    <img src="assets/Рисунок16.png">
</div>

### Итог
На этом установка необходимого ПО завершена.
Необходимо переходить к инструкциям по настройке VS Code и использование GitHub
</details>

<details>
<summary>Ubuntu</summary>

### Установка VS Code
<details>
<summary>Через пакет</summary>
<br/>

- Переходим на сайт code.visualstudio.com, секция Download. Нажимаем и скачиваем себе на ПК.
- Устанавливаем
</details>

<details>
<summary>Через терминал</summary>

1. Заходим на оф.сайт https://code.visualstudio.com/docs/setup/setup-overview и выбираем Linux. По инструкции вводим следующие команды в терминал для Убунту

`sudo apt-get install wget gpg`\
`wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg`\
`sudo install -D -o root -g root -m 644 packages.microsoft.gpg /etc/apt/keyrings/packages.microsoft.gpg`\
`sudo sh -c 'echo "deb [arch=amd64,arm64,armhf signed-by=/etc/apt/keyrings/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" > /etc/apt/sources.list.d/vscode.list'`\
`rm -f packages.microsoft.gpg`\
`sudo apt install apt-transport-https`\
`sudo apt update`\
`sudo apt install code`
</details>

### Установка Node.js

- Ввести в терминал `sudo apt update`
- `sudo apt install nodejs`
-  Проверить можно командой `node -v`или `nodejs -v`. Должен показаться номер вашей версии Node.js

### Установка Git

- Ввести в терминал
`sudo apt update`\
Возможно, вас попросят ввести пароль. Введите пароль. <strong>Внимание:</strong> его не будет видно в терминале, это нормально.

`sudo apt upgrade`\
`sudo apt install git`

- Можно проверить, что у вас установился `git`, введя в терминале `git`. Должен открыться список команд.

### Настройка Git

1. В терминале необходимо ввести две команды
`git config --global user.name "Ваш никнейм на github"`
`git config --global user.email ВашEmailНаGithub@example.com`
2. Проверяем коммандой `git config --list`

### Генерация ключа  SSH

1. Открываем терминал
2. Вводим команду `ssh-keygen -t ed25519 -C "ваш_email@example.com"`
3. Приложение запросит место сохранения, предлагая по умолчанию, нажимаем `Enter`
4. Далее вам будет предложено ввести кодовую фразу. Нажмите клавишу `Enter`, чтобы пропустить
5. Подтверждение кодовой фразы также пропускаем
6. После генерации идем по пути из 3го пункта и открываем файл `id_ed25519.pub` любым текстовым редактором и копируем содержимое.
7. Идем в настройки аккаунта на GitHub

<div align="center">
    <img src="assets/Рисунок15.png" width="200">
</div>

8. Нажимаем кнопку New SSH Key и в открывшемся окне вставляем содержимое из файла `id_ed25519.pub` и вводим название ключа

<div align="center">
    <img src="assets/Рисунок16.png">
</div>

### Итог

На этом установка необходимого ПО завершена.
Необходимо переходить к инструкциям по настройке VS Code и использование GitHub
</details>

<details>
<summary>MacOS</summary>

### Установка VS Code

1. Заходим на оф.сайт https://code.visualstudio.com/docs/setup/setup-overview и выбираем macOS. По инструкции открываем первую ссылку и скачиваем пакет в виде архива.
2. Нам необходимо распаковать архив и перетащить `Visual Studio Code.app` в папку `Applications`.
3. Добавим Visual Studio Code в `Dock`, выбрав в `Options` `«Keep in Dock»`

### Установка Git

- Если у вас нет пакетного менеджера Brew, необходимо сначала установить его. Переходит на оф. сайт и https://brew.sh/ и копируем команду оттуда
`/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`
- Затем вводим в терминал `brew install git`
- Можно проверить, что у вас установился `git`, введя в терминале `git`. Должен открыться список команд.

### Установка Node.js

- Ввести в терминал `brew update`
- `brew install node`
-  Проверить можно командой `node -v. Должен показаться номер вашей версии Node.js

### Настройка Git

1. В терминале необходимо ввести две команды
`git config --global user.name "Ваш никнейм на github"`
`git config --global user.email ВашEmailНаGithub@example.com`
2. Проверяем коммандой `git config --list`

### Генерация ключа  SSH

1. Открываем терминал
2. Вводим команду `ssh-keygen -t ed25519 -C "ваш_email@example.com"`
3. Приложение запросит место сохранения, предлагая по умолчанию, нажимаем `Enter`
4. Далее вам будет предложено ввести кодовую фразу. Нажмите клавишу `Enter`, чтобы пропустить
5. Подтверждение кодовой фразы также пропускаем
6. После генерации идем по пути из 3го пункта и открываем файл `id_ed25519.pub` любым текстовым редактором и копируем содержимое.
7. Идем в настройки аккаунта на GitHub

<div align="center">
    <img src="assets/Рисунок15.png" width="200">
</div>

8. Нажимаем кнопку New SSH Key и в открывшемся окне вставляем содержимое из файла `id_ed25519.pub` и вводим название ключа

<div align="center">
    <img src="assets/Рисунок16.png">
</div>

### Итог

На этом установка необходимого ПО завершена.
Необходимо переходить к инструкциям по настройке VS Code и использование GitHub
</details>
