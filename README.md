### 1. Создать SSH-ключ, заменив `your_email@example.com` на почту GitHub:

```
ssh-keygen -t ed25519 -C "your_email@example.com" -f ~/.ssh/github
```

### 2. Активировать и добавить ключ в SSH-агент:

```
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/github
```

### 3. Добавить ключ на GitHub:

```
cat ~/.ssh/github.pub
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
  IdentityFile ~/.ssh/github
```

### 5. Проверить соединение:

```
ssh -T git@ssh.github.com
```

### 6. Клонировать с GitHub с помощью команды:

```
git clone git@github.com:username/example_repository.git
```
