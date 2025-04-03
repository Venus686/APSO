# CONTENIDO
• /etc/apt/sources.list -> es un archivo de configuración de fuente, el cual apt usa para descargar e instalar paquetes. \


• aptitude -> Debian y ubuntu, es una alternativa para apt y apt -get\
EJEMPLO : sudo aptitude install plank\

• apt-get -> Actualiza, instala, elimina o limpia un paquete\
Ej:sudo apt -get aptitude\

• apt-cache -> muestra información sobre paquetes en el sistema\
     showpkg. Muestra alguna información general para un sólo paquete\
     stats. Muestra algunas estadísticas básicas\
     dump. Muestra el archivo entero en un formato terso\
     unmet. Muestra dependencias incumplidas\
     search. Busca en la lista de paquetes por un patrón de expresión regular\
     show. Muestra un registro legible para el paquete\
     depends. Muestra la información de dependencias en bruto para el paquete \
EJ: sudo apt-cache search devede\

• add-apt-repository -> Agrega repositorios de software en sistemas basados en APT.\
sudo add-apt-repository ppa:docky-core/stable \

GZIP
• tar -> Utilizado para comprimir y descomprimir archivos en formatos .tar, .tar.gz, etc.\
.Instale el paquete descargado.
tar xvfz AdobeReader_esp-8.1.7-1.i486.tar.gz
cd AdobeReader/
sudo ./INSTALL
Para comprimir un archivo individual usando gzip:\
gzip nombre_archivo_comprimido \
• Para descomprimir un archivo individual gzipeado:\
gunzip nombre_archivo_comprimido\
• Para crear un archivo tar gzipeado:\
tar cvzf nombre_archivo_comprimido.tar\
nombre_archivo_a_comprimir\
• Para extraer archivos específicos de un archivo tar gzipeado:\
tar xvzf nombre_archivo_comprimido.tar\
nombres_archivos_a_extraer\

• snap -> Sistema de paquetes desarrollado por Canonical para instalar software de manera aislada.\
snap list /snap --help/ snap find / snap remove

• flatpak -> Similar a snap, permite instalar aplicaciones en un entorno independiente.\
list /search /install /uinstall

• /etc/passwd -> Archivo con información de las cuentas de usuario (nombre, UID, GID, etc.).\
• /etc/shadow -> Archivo con las contraseñas cifradas de los usuarios.
• /etc/group -> Contiene los grupos del sistema y los usuarios que pertenecen a ellos.
• /etc/adduser.conf ->   Archivo de configuración predeterminado para la creación de nuevos usuarios.
• adduser -> Comando para agregar usuarios de manera más amigable que useradd.
• addgroup -> Crea nuevos grupos en el sistema.
• usermod ->  Modifica cuentas de usuario (cambia grupo, directorio home, etc.).
• deluser ->  Elimina un usuario del sistema.
• delgroup -> Elimina un grupo del sistema.
• chsh -> Cambia el shell predeterminado de un usuario.
• chage -> Gestiona la caducidad de contraseñas de los usuarios.

ulimit → Establece límites de uso de recursos para procesos en ejecución.
quotachek → Escanea el sistema de archivos y genera información sobre cuotas de usuario.
quotaon → Activa las cuotas de disco en el sistema.
quotaoff → Desactiva las cuotas de disco.
quota → Muestra el uso de cuota de disco de un usuario.
edquota → Permite editar las cuotas de disco de un usuario.
repquota → Genera un informe sobre el uso de cuota en el sistema.

/etc/default/grub → Archivo de configuración de GRUB (gestor de arranque).
Cosas que se pueden modificar (tienes que PONER SUDO):\
Antes de modificarlo hay que hacerle una copia al archivo\
Tiempo de elección del menú -> GRUB_TIMEOUT=60\
La resolución inicial -> GRUB_GFXMODE=800x600\
NO RECOVERY MODE -> GRUB_DISABLE_RECOVERY="true" \
Pitido al aparecer el menú -> GRUB_INIT_TUNE \

update-grub2 → Actualiza la configuración de GRUB tras cambios en /etc/default/grub.
sudo update-grub2

Cosas que se pueden modificar (tienes que PONER SUDO):\
Antes de modificarlo hay que hacerle una copia al archivo\
Tiempo de elección del menú -> GRUB_TIMEOUT=60\
La resolución inicial -> GRUB_GFXMODE=800x600\
NO RECOVERY MODE -> GRUB_DISABLE_RECOVERY="true" \
Pitido al aparecer el menú -> GRUB_INIT_TUNE

dmesg → Muestra los mensajes del kernel (útil para depuración de hardware).
dmesg | grep EXT4

systemctl → Gestiona servicios y procesos en sistemas con systemd.
systemctl list-units --type=service --state=active
$ sudo systemctl start servicio
$ sudo systemctl stop servicio
$ sudo systemctl enable servicio
$ sudo systemctl disable service
$ sudo systemctl mask servicio
$ sudo systemctl unmask servicio

journalctl → Permite ver los logs del sistema en systemd.
• journalctl -b nos muestra los mensajes del arranque
• journalctl -f permite seguir los mensajes nuevos

pstree → Muestra los procesos en ejecución en forma de árbol.
cron → Servicio para programar tareas automáticas en horarios específicos.
at → Programa la ejecución de comandos en un tiempo específico.
at 00:32
warning: commands will be executed using /bin/sh
at> echo " linea generada por la orden at a las $(date)" >> /home/userapso/cadahora
at> <EOT>
at> CTRL-D (para finalizar)
at -f programado now + 15 min

shutdown → Apaga o reinicia el sistema.
sudo shutdown -h +2 "salid y guardar que esto se va a apagar"
