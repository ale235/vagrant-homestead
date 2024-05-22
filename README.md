# vagrant-homestead
#Requerimientos Previos

- VirtualBox
- Vagrant

#Instalación

 1.1: home/user/Proyectos

```bash

vagrant box add laravel/homestead

```
1.2 

```bash
git clone https://github.com/laravel/homestead.git ~/Proyectos/Homestead
```
1.3 

Posicionarse en la carpeta del proyecto y luego hacer un checkout en la rama "release"
```bash
cd ~/Proyectos/Homestead
git checkout release
```
1.4 

```bash
//En caso de linux
bash init.sh
```
```bash
//En caso de windows
.\init.bat
```

#Levantar la VM

```bash
vagrant up
```

En caso que devuelta

```
acolautti@ubuntu:~/Proyectos/Homestead$ vagrant up
/home/acolautti/.vagrant.d/gems/2.4.6/gems/rubyhacks-0.1.5/lib/rubyhacks.rb:536: warning: constant ::Fixnum is deprecated
proxyconf...
se encontro el plugin proxyconf !
http_proxy: http://10.10.254.218:3128/
https_proxy: http://10.10.254.218:3128/
no_proxy: 10.,192.168.,.sfnet,wpad,127.0.0.1,localhost,mirror.santafe.gov.ar,.santafe.gov.ar,.santafe.gob.ar,.santa-fe.gob.ar
Check your Homestead.yaml (or Homestead.json) file, the path to your private key does not exist.

```
Correr

```bash
ssh-keygen -t rsa -b 4096 -C "acolautti@homestead"
```
#Modificar el Homestead.yml con el mapeo
```
folders:
  - map: C:/Github/Ale/zeus
    to: /home/vagrant/code

```
Siempre luego de moficiar el Homesteard yml hay que correr el provision
```
vagrant reload --provision
```

```bash
vagrant ssh
```

```bash
composer create-project --prefer-dist laravel/laravel blog
```

#Referencias
https://stackoverflow.com/questions/44463987/homestead-installation
