
# Configuración de claves SSH para GitHub y GitLab

Este archivo te guiará para configurar tus claves SSH y enlazarlas a tus cuentas de **GitHub** y **GitLab**.

## 1. Generar una nueva clave SSH  
   Ejecuta el siguiente comando para generar una nueva clave SSH para **GitLab**:

   ```bash
   ssh-keygen -t rsa -b 4096 -C "arturoletonaporras2024@gmail.com" -f ~/.ssh/id_rsa_gitlab
   ```

## 2. Ver la clave pública  
   Para ver la clave pública generada, usa el siguiente comando:

   ```bash
   cat ~/.ssh/id_rsa_gitlab.pub
   ```

## 3. Configuración de SSH  
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
       IdentityFile ~/.ssh/id_rsa

   # Configuración para GitLab
   Host gitlab.com
       HostName gitlab.com
       User git
       IdentityFile ~/.ssh/id_rsa_gitlab
   ```

## 4. Verificar la conexión  
   Verifica la conexión con **GitLab** usando el siguiente comando:

   ```bash
   ssh -T git@gitlab.com
   ```

   Cuando se te pida, escribe `yes` para continuar.

## 5. Subir cambios a GitLab  
   Una vez configurado, puedes subir tus cambios a **GitLab** con los siguientes pasos:

   1. Verifica tu rama actual:

   ```bash
   git branch
   ```

   2. Añade los archivos al área de preparación:

   ```bash
   git add .
   ```

   3. Haz commit de los cambios:

   ```bash
   git commit -m "blablá"
   ```

   4. Asegúrate de usar el siguiente comando para hacer push a **GitLab**:

   ```bash
   git push --set-upstream gitlab main
   ```

   Este comando es necesario para establecer la rama principal (`main`) en GitLab.

---

¡Con estos pasos, deberías tener correctamente configurado tu acceso SSH tanto para **GitHub** como para **GitLab**!
