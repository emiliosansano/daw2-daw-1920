# daw2-daw-1920

## clase 1

- Crear una cuenta en github
- Crear un nuevo repositorio: daw2-daw-1920
- instalar git
- Si aparece un error "no se pudo bloquear /var/lib/dpkg/lock" ..., introducir la siguiente instrucción:

```
sudo fuser -vki /var/lib/dpkg/lock
```

y volver a instalar git. 

```
sudo apt install git 
```

### Instrucciones básicas git
- Clonar el repositorio remoto
```
git clone url
```

- Ver estado del repositorio local
```
git status 
```

- Hacer un *commit* (comprometer) los cambios al repositorio local
```
git commit -am "mensaje"
```

- Subir (push) los cambios del repositorio local el repositorio remoto:

```
git push origin master
```

- Actualizar (pull) el repositorio local con los cambios desde el repositorio remoto

```
git pull origin master
```

### Añadir clave ssh a github

En primer lugar instalamos openssh-server:
```
sudo apt install openssh-server
```

Después generamos una clave:
```
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```
Una vez generada la clave, la copiamos al portapapeles. Para ello, mostramos la clave por la consola del sistema, y luego la copiamos:
```
cat ~/.ssh/id_rsa.pub
```

y la añadimos a github (**settigs** -> **SSH and PGP keys**)

Arrancamos el agente *ssh* en segundo plano:
```
eval "$(ssh-agent -s)"
```

y ahora añadimos la clave al agente:
```
ssh-add ~/.ssh/id_rsa
```

Para que github acepte la conexión ssh hay que modificar la dirección *origin*. Para ver la url actual:
```
git remote show origin
```

Esto nos mostrará un mensaje similar a este:
```
URL  para obtener: https://github.com/emiliosansano/daw2-daw-1920.git
URL para publicar: https://github.com/emiliosansano/daw2-daw-1920.git
  
```

Ahora hay que modificar esta dirección añadiento la opción *ssh*:
```
git remote set-url origin git+ssh://git@github.com/tu-usuario/daw2-daw-1920.git

```

## Instalación de virtualbox
- Primero instalamos las dependencias:
```
sudo apt install libcurl4 libqt5opengl5 libqt5printsupport5
sudo apt install gcc make perl
```

- Descargamos virtualbox y el *extension pack* desde la página de descargas de www.virtualbox.org
- Ejecutamos el archivo .deb descargado:
```
sudo dpkg -i virtualbox-6.0_6.0.12-133076~Ubuntu~bionic_amd64.deb
```

