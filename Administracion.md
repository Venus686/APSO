# CONTENIDO
• /etc/apt/sources.list -> es un archivo de configuración de fuente, el cual apt usa para descargar e instalar paquetes. \
Cosas que se pueden modificar (tienes que PONER SUDO):\
Antes de modificarlo hay que hacerle una copia al archivo\
Tiempo de elección del menú -> GRUB_TIMEOUT=60\
La resolución inicial -> GRUB_GFXMODE=800x600\
NO RECOVERY MODE -> GRUB_DISABLE_RECOVERY="true" \
Pitido al aparecer el menú -> GRUB_INIT_TUNE

• aptitude -> Debian y ubuntu, es una alternativa para apt y apt -get
EJEMPLO : sudo aptitude install plank

• apt-get -> Actualiza, instala, elimina o limpia un paquete
Ej:sudo apt -get aptitude

• apt-cache -> muestra información sobre paquetes en el sistema
• add-apt-repository -> Agrega repositorios de software en sistemas basados en APT.
• tar -> Utilizado para comprimir y descomprimir archivos en formatos .tar, .tar.gz, etc.
• snap -> Sistema de paquetes desarrollado por Canonical para instalar software de manera aislada.
• flatpak -> Similar a snap, permite instalar aplicaciones en un entorno independiente.



• /etc/passwd -> Archivo con información de las cuentas de usuario (nombre, UID, GID, etc.).
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

• ulimit ->
• quotachek ->
• quotaon ->
• quotaoff ->
• quota ->
• edquota ->
• repquota ->

• /etc/default/grub ->
• update-grub2 ->
• dmesg ->
• systemctl ->
• journalctl ->
• pstree ->
• cron ->
• at ->
• shutdown ->
