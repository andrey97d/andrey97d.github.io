# Git: шпаргалка

## Ежедневный минимум

```bash
git status
git fetch -p
git pull
```

## Создать ветку
```bash
git switch -c feature/my-task
```

## Посмотреть ветки
```bash
git branch
git branch -a
git branch -r
```

## Закоммитить изменения
```bash
git add .
git commit -m "feat: short description"
```
## Отправить ветку 
```bash
git push -u origin feature/my-task
```

## Посмотреть историю репозитория
```bash
git log --oneline --graph --decorate --all
```

## Спрятать изменения и вернуть
```bash
git stash
git stash pop
```

## Очистить удаленные ветки
```bash
git fetch -p
```

## Безопасный force push
```bash
git push --force-with-lease
```

## Если что-то сломалось
```bash
git status
git reflog
```
