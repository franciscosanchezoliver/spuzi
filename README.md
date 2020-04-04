- Recuperamos el nombre del dispositivo (pendrive en mi caso)
	sudo fdisk -l

  Esto me dio para el pen el siguiente resultado

=================
isk /dev/sdb: 14.46 GiB, 15514730496 bytes, 30302208 sectors
Disk model: USB DISK 2.0    
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disklabel type: dos
Disk identifier: 0x00224e0b

Device     Boot Start      End  Sectors  Size Id Type
/dev/sdb1  *     2048 30302207 30300160 14.5G  c W95 FAT32 (LBA)
=================

Vemos como linux indentifica la memoria como "/dev/sdb".

Para recuperar los archivos ejecutamos el siguiente comando
sudo foremost -t all -i /dev/sdb -o ~/un_directorio_para_recuperar

-t all: quiere decir que recupere todo tipo de archivos. Foremost puede recuperar un monton de tipos de archivos, podemos ver o aniadir los tipos de archivos que queremos recuperar en el siguiente archivo: /etc/foremost.conf

-i /dev/sdb: aqui indicamos el dispositivo del que queremos recuperar los archivos.

-o ~/un_directorio_para_recuperar: aqui se pondra la informacion que se haya podido recuperar
