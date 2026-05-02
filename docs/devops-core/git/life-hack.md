# Git: команды и лайфхаки

## Быстрая синхронизация

```bash
git status
git fetch -p
git pull
```
## Очистить удаленные ветки
```bash
git fetch --prune
```

или

```bash
git remote prune origin
```

## Посмотреть ветки

```
git branch      # локальные ветки
git branch -r   # удалённые ветки
git branch -a   # все ветки
```

## Создать ветку и перейти в нее
```
git switch -c feature/my-task
```