# 🚀 Как создать свой сайт с нуля

Полный гайд: домен → VPS → nginx → Cloudflare → CI/CD.

---

## 📦 Что понадобится

- домен (reg.ru)
- VPS (любой самый минимальный)
- GitHub (обязательно публичный)
- MkDocs (утилита из репозитория pip)

---

## Подготовка
### 1) Приобретаем VPS
тут подойдет любая конфигурация (например 1CPU, 1GbRAM, 20Gb SSD)

!!! warning "Chinese, Japanese and Korean characters"

    Reading time computation currently does not take segmentation of Chinese,
    Japanese and Korean characters into account. This means that the reading
    time for posts in these languages may be inaccurate. We're planning on
    adding support in the future. In the meantime, please use the `readtime`
    front matter property to set the reading time.

### 2) Приобретаем доменное имя
выбирайте любое свободное название и затем перейдите в настройки DNS
Нам нужно создать A запись которая будет связана к ip адресу вашего VPS

Например: A docs.devopslearning.ru - 10.10.10.1

### 3) Создаем GIT репозиторий
Можно использовать что угодно, я покажу пример на GitHub.
> Важно чтобы репозиторий был публичным (не приватным)
### 4) Подготоваливаем нашу рабочую машину (не VPS)
Проверьте что на вашем личном устройстве установлен python3 и pip

##### 4.1 Клонируем созданный репозиторий и переходим в папку проекта
```console
$ git clone <ваш репозиторий>
$ cd <название вашего репозитория>
```

##### 4.2 Создаем виртуальное окружение python и активируем его
```console
$ python3 -m venv .
$ source venv/bin/activate
```
##### 4.3 Устанавливаем утилиту mkdocs
```
pip install mkdocs-material
```
Появятся файлы mkdocs.yml и docs/index.md

##### 4.4 Создаем проект
```
mkdocs new .
```
##### 4.5 Настраиваем mkdocs.yml (минимально)
```
site_name: My Docs
site_url: https://docs.devopslearning.ru

theme:
  name: material
```

##### 4.6 Запускаем локально
```
mkdocs serve
```
Открываем http://127.0.0.1:8000

#####  4.7 Создаем наши страницы
1) Добавляем будущие страницы 
```console
$ mkdir docs/how-to
$ touch docs/how-to/create-website.md
```
2) Подключаем к навигации
в mkdocs.yaml добавляем новый раздел
```console
nav:
  - Главная: index.md
  - Гайды:
      - Создание сайта: how-to/create-website.md
```

3) Оформляешь страницы в формате Markdown

4) Вводишь команду в терминале
```console
$ mkdocs build
```
Появляется папка site, в которой уже в формате html описан файл который вы написали на Markdown.

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
