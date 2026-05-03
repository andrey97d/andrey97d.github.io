

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
