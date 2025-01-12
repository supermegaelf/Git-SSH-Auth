1. Сгенерировать ключ, выбрать дирректорию для SSH ключа `/root/.ssh/github.pub`:

```
ssh-keygen -t ed25519 -C "your_email@example.com"
```

2. Тест:

```
ssh -vT git@github.com
```

3. Отобразить список всех удалённых репозиториев, настроеных для вашего локального репозитория Git:

```
git remote -v
```

Если вывод такой: `https://github.com/supermegaelf/Marzban-Subscription-Page.git`

Нужно исправить, чтобы строка выше начиналась не с `https`, а с `git`.

4. Удалить удалённый репозиторий:

```
git remote rm origin
```

5. Добавить новый удалённый репозиторий:

```
git remote add origin git@github.com:supermegaelf/Marzban-Subscription-Page.git
```

После этого `git push origin master` будет работать.
