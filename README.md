# Instalacion de ansible automation 2.3

1. Instalar los nodos con RHEL 9.1 con usuario root
2. Poner el nombre correcto de cada nodo (es necesario cambiar el hostname porque la instalacion de ansible no se puede realizar como localhost)
```bash
hostnamectl status
sudo hostnamectl set-hostname controller.ger.mx
```
3. Agregar los host en /etc/hosts
```bash
sudo vi /etc/hosts

192.168.100.138 controller.ger.mx
192.168.100.252 hub.ger.mx
```
4. Crear las llaves con:
```bash
ssh-keygen -f .ssh/key-with-pass
```
5. Copiar las credenciales en los nodos y validar que se conecte sin requerir contraseña
```bash
ssh-copy-id -i .ssh/key-with-pass.pub root@controller.ger.mx
ssh root@controller.ger.mx
```
4.Se debe descargar ansible automation y adjunto los archivos de inventario del controller y del hub, importante en cada nodo se debe especificar el usuario