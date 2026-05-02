

## Создать ветку
```bash
git switch -c feature/my-task
```
## Переключиться на ветку
```bash
git switch main
```

## Переименовать ветку
```bash
git branch -m new-branch-name
```
## Удалить ветку
```bash
git branch -d feature/my-task
```
## Принудительно удалить ветку
```bash
git branch -D feature/my-task
```
## Удалить удаленную ветку
```bash
git push origin --delete feature/my-task
```

## Очистить удаленные ветки
```bash
git fetch -p
```
или 
```bash
git remote prune origin
```
