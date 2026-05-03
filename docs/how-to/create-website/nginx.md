
### 5) Настройка nginx (VPS)

После того как вы подготовили свои страницы и через команду ```mkdocs serve ``` удовлетворены результатом мы перенесем эти страницы на наш сервер, но для начала мы превратим наш сервер в веб-сервер.

##### 5.1 Устанавливаем NGINX
Освежим список пакетов и обновим их до последних версий
```console
$ sudo apt update && sudo apt upgrade -y
```

Установим приложение nginx
```console
$ sudo apt install -y nginx
```

Проверим работоспособность
```console
$ sudo systemctl status nginx
```
Ожидаемый результат команды:
```console
nginx.service - A high performance web server and a reverse proxy server
     Loaded: loaded (/usr/lib/systemd/system/nginx.service; enabled; preset: enabled)
     Active: active (running) since Fri 2026-04-24 22:09:08 CEST; 1 day 23h ago

```

Переносим site на VPS
```
rsync -avz --delete site/ user@ip_remote_host:/var/www/docs/
```
