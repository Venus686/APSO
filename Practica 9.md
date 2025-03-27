# CONTENIDO
• /etc/default/grub
• update-grub2
• dmesg
• systemctl
• journalctl
• pstree
• cron
• at
• shutdown

lucia@lucia-VirtualBox:~$ sudo cp /etc/default/grub /etc/default/grub.original \
lucia@lucia-VirtualBox:~$ sudo joe /etc/default/grub \
GRUB_TIMEOUT_STYLE=hidden -> a menu \
GRUB_TIMEOUT=0 -> a 60 \
#GRUB_DISABLE_RECOVERY="true" \
#GRUB_GFXMODE=640x480 -> 800x600 \

/etc/grub.d \
chmod a-x ./20_memtest86+ \

update-grub2 (basandose en los nucleos disponibles y en los ficheros que tengas)\
Para saner si ha funcionado hay que arrancas de nuevo.\

