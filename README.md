
# Configuración de claves SSH para GitHub y GitLab

Este archivo te guiará para configurar tus claves SSH y enlazarlas a tus cuentas de **GitHub** y **GitLab**.

Para **GitLab**, ejecuta el siguiente comando para generar una nueva clave SSH:

```bash
ssh-keygen -t rsa -b 4096 -C "arturoletonaporras2024@gmail.com" -f ~/.ssh/id_rsa_gitlab
```

Para **GitHub**, ejecuta este comando (usaremos un archivo diferente para cada plataforma):

```bash
ssh-keygen -t rsa -b 4096 -C "arturoletonaporras2024@gmail.com" -f ~/.ssh/id_rsa_github
```

Para ver la clave pública de **GitLab**, usa:

```bash
cat ~/.ssh/id_rsa_gitlab.pub
```

Para ver la clave pública de **GitHub**, usa:

```bash
cat ~/.ssh/id_rsa_github.pub
```

Edita el archivo de configuración de SSH:

```bash
nano ~/.ssh/config
```

Agrega el siguiente código al archivo `config`:

```bash
# Configuración para GitHub
Host github.com
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_rsa_github

# Configuración para GitLab
Host gitlab.com
    HostName gitlab.com
    User git
    IdentityFile ~/.ssh/id_rsa_gitlab
```

Verifica la conexión con **GitLab** usando el siguiente comando:

```bash
ssh -T git@gitlab.com
```

Luego verifica la conexión con **GitHub**:

```bash
ssh -T git@github.com
```

Cuando se te pida, escribe `yes` para continuar en cada caso.

Con estos pasos, deberías tener correctamente configurado tu acceso SSH tanto para **GitHub** como para **GitLab**.
