# Общая инфа



### Создание виртуального окружения

```bash
python3 -m venv .venv
source .venv/bin/activate
```


### Отключаем предупреждения по сертификатам
```python
import requests
import urllib3
requests.packages.urllib3.disable_warnings()
```

### 