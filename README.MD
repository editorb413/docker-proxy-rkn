DOCKER-READY Telegram proxy

Авторизуемся в хероку
```bash
heroku login
heroku:container login
```

Сборка билда на М1
```bash
docker buildx build --platform linux/amd64 -t appname .
```

Создание тега для билда
```bash
docker tag appname registry.heroku.com/appname/web
```

Пушим билд в хероку
```bash
docker push registry.heroku.com/appname/web
```

Релиз сборки
```bash
heroku container:release web -a appname
```


`appname` везде заменяем на имя приложения хероку
