### 1. Создать SSH-ключ, заменив `your_email@example.com` на почту GitHub:

```
ssh-keygen -t ed25519 -C "your_email@example.com"
```

### 2. Активировать и добавить ключ в SSH-агент:

```
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/git
```

### 3. Добавить ключ на GitHub:

```
cat ~/.ssh/git.pub
```

> [!NOTE]
> [SSH keys](https://github.com/settings/keys)

### 4. Настроить SSH-конфигурацию:

```
nano ~/.ssh/config
```

Добавить:

```
Host github
  HostName github.com
  User git
  Port 2222
  IdentityFile ~/.ssh/id_ed25519
```

### 5. Проверить соединение:

```
ssh -T github
```

### 6. Клонировать с GitHub с помощью команды:

```
git clone git@github.com:username/example_repository.git
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
