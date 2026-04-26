# 🚀 Как создать свой сайт с нуля

Полный гайд: домен → VPS → nginx → Cloudflare → CI/CD.

---

## 📦 Что понадобится

- домен (reg.ru)
- VPS
- GitHub
- MkDocs

---

## Подготовка
### Приобретаем VPS
тут подойдет любая конфигурация, на ваш вкус и цвет
### Приобретаем доменное имя
лично я покупал на reg.ru.
### Создаем GIT репозиторий
Можно использовать что угодно, я покажу пример на GitHub.
Важно чтобы репозиторий был публичным (не приватным)
### Подготоваливаем нашу рабочую машину (не VPS)
Проверьте что на вашем личном устройстве установлен python3 и pip




```console
$ docker compose up -d
$ ./run_tests
$ docker compose down
```


> [!TIP]
> 
> If you have already installed Docker Desktop, you can check which version of Compose you have by selecting **About Docker Desktop** from the Docker menu 


![whale menu](/../desktop/images/whale-x.svg).

### Plugin (Linux only)

> [!IMPORTANT]
>
> This method is only available on Linux.
