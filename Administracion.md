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

• apt-cache -> 
• add-apt-repository
• tar
• snap
• flatpak



• /etc/passwd
• /etc/shadow
• /etc/group
• /etc/adduser.conf
• adduser
• addgroup
• usermod
• deluser
• delgroup
• chsh
• chage
• ulimit
• quotachek
• quotaon
• quotaoff
• quota
• edquota
• repquota

• /etc/default/grub
• update-grub2
• dmesg
• systemctl
• journalctl
• pstree
• cron
• at
• shutdown
