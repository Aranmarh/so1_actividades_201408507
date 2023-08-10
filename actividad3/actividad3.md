# Actividad 3
## Parte 1 Gestión de Usuarios

```bash
ran@aran-IdeaPad-5-15IIL05:~$ sudo su
[sudo] password for aran:
root@aran-IdeaPad-5-15IIL05:/home/aran# adduser usuario1
Adding user 'usuario1' ...
Adding new group 'usuario1' (1001) ...
Adding new user 'usuario1' (1001) with group 'usuario1' ...
Creating home directory '/home/usuario1' ...
Copying files from '/etc/skel' ...
New password:
Retype new password:
Sorry, passwords do not match.
passwd: Authentication token manipulation error
passwd: password unchanged
Try again? [y/N] y
New password:
Retype new password:
passwd: password updated successfully
Changing the user information for usuario1
Enter the new value, or press ENTER for the default
	Full Name []: usuario1
	Room Number []: usuario1
	Work Phone []: 12345678
	Home Phone []:
	Other []:
Is the information correct? [Y/n] y
root@aran-IdeaPad-5-15IIL05:/home/aran# adduser usuario2
Adding user 'usuario2' ...
Adding new group 'usuario2' (1002) ...
Adding new user 'usuario2' (1002) with group 'usuario2' ...
Creating home directory '/home/usuario2' ...
Copying files from '/etc/skel' ...
New password:
Retype new password:
passwd: password updated successfully
Changing the user information for usuario2
Enter the new value, or press ENTER for the default
	Full Name []: usuario2
	Room Number []:
	Work Phone []: 12345678
	Home Phone []:
	Other []:
Is the information correct? [Y/n] y
root@aran-IdeaPad-5-15IIL05:/home/aran# adduser usuario3
Adding user 'usuario3' ...
Adding new group 'usuario3' (1003) ...
Adding new user 'usuario3' (1003) with group 'usuario3' ...
Creating home directory '/home/usuario3' ...
Copying files from '/etc/skel' ...
New password:
Retype new password:
passwd: password updated successfully
Changing the user information for usuario3
Enter the new value, or press ENTER for the default
	Full Name []: usuario3
	Room Number []:
	Work Phone []: 12345678
	Home Phone []:
	Other []:
Is the information correct? [Y/n] y
root@aran-IdeaPad-5-15IIL05:/home/aran# id usuario1
uid=1001(usuario1) gid=1001(usuario1) groups=1001(usuario1)
root@aran-IdeaPad-5-15IIL05:/home/aran# userdel -r usuario3
userdel: usuario3 mail spool (/var/mail/usuario3) not found
root@aran-IdeaPad-5-15IIL05:/home/aran# ^C
root@aran-IdeaPad-5-15IIL05:/home/aran# userdel -r usuario3
userdel: user 'usuario3' does not exist
root@aran-IdeaPad-5-15IIL05:/home/aran# ^C
root@aran-IdeaPad-5-15IIL05:/home/aran# userdel -r usuario3
userdel: user 'usuario3' does not exist
root@aran-IdeaPad-5-15IIL05:/home/aran# id usuario3
id: 'usuario3': no such user
root@aran-IdeaPad-5-15IIL05:/home/aran# id usuario1
uid=1001(usuario1) gid=1001(usuario1) groups=1001(usuario1)
root@aran-IdeaPad-5-15IIL05:/home/aran# id usuario2
uid=1002(usuario2) gid=1002(usuario2) groups=1002(usuario2)
root@aran-IdeaPad-5-15IIL05:/home/aran# adduser usuario3
Adding user 'usuario3' ...
Adding new group 'usuario3' (1003) ...
Adding new user 'usuario3' (1003) with group 'usuario3' ...
Creating home directory '/home/usuario3' ...
Copying files from '/etc/skel' ...
New password:
Retype new password:
passwd: password updated successfully
Changing the user information for usuario3
Enter the new value, or press ENTER for the default
	Full Name []: usuario3
	Room Number []:
	Work Phone []: 12345678
	Home Phone []:
	Other []:
Is the information correct? [Y/n] y
root@aran-IdeaPad-5-15IIL05:/home/aran# userdel -r usuario
```
##  Parte 2: Gestión de Grupos
```bash
root@aran-IdeaPad-5-15IIL05:/home/aran# usermod -aG grupo1 usuario1
root@aran-IdeaPad-5-15IIL05:/home/aran# usermod -aG grupo2 usuario2
root@aran-IdeaPad-5-15IIL05:/home/aran# id usuario1
uid=1001(usuario1) gid=1001(usuario1) groups=1001(usuario1),1003(grupo1)
root@aran-IdeaPad-5-15IIL05:/home/aran# id usuario2
uid=1002(usuario2) gid=1002(usuario2) groups=1002(usuario2),1004(grupo2)
root@aran-IdeaPad-5-15IIL05:/home/aran# groups usuario1
usuario1 : usuario1 grupo1
root@aran-IdeaPad-5-15IIL05:/home/aran# groups usuario2
usuario2 : usuario2 grupo2
root@aran-IdeaPad-5-15IIL05:/home/aran# groupdel grupo2
ran@aran-IdeaPad-5-15IIL05:~$ cat /etc/group
root:x:0:
daemon:x:1:
bin:x:2:
sys:x:3:
adm:x:4:syslog,aran
tty:x:5:syslog
disk:x:6:
lp:x:7:
mail:x:8:
news:x:9:
uucp:x:10:
man:x:12:
proxy:x:13:
kmem:x:15:
dialout:x:20:
fax:x:21:
voice:x:22:
cdrom:x:24:aran
floppy:x:25:
tape:x:26:
sudo:x:27:aran
audio:x:29:pulse
dip:x:30:aran
www-data:x:33:
backup:x:34:
operator:x:37:
list:x:38:
irc:x:39:
src:x:40:
gnats:x:41:
shadow:x:42:
utmp:x:43:
video:x:44:
sasl:x:45:
plugdev:x:46:aran
staff:x:50:
games:x:60:
users:x:100:
nogroup:x:65534:
systemd-journal:x:101:
systemd-network:x:102:
systemd-resolve:x:103:
systemd-timesync:x:104:
crontab:x:105:
messagebus:x:106:
input:x:107:
kvm:x:108:
render:x:109:
syslog:x:110:
tss:x:111:
bluetooth:x:112:
ssl-cert:x:113:
uuidd:x:114:
tcpdump:x:115:
avahi-autoipd:x:116:
rtkit:x:117:
ssh:x:118:
netdev:x:119:
lpadmin:x:120:aran
avahi:x:121:
scanner:x:122:saned
saned:x:123:
nm-openvpn:x:124:
whoopsie:x:125:
colord:x:126:
geoclue:x:127:
pulse:x:128:
pulse-access:x:129:
gdm:x:130:
lxd:x:131:aran
aran:x:1000:
sambashare:x:132:aran
systemd-coredump:x:999:
docker:x:133:aran
mysql:x:134:
usuario1:x:1001:
usuario2:x:1002:
grupo1:x:1003:usuario1


```

##  Parte 3: Gestión de Permisos
```bash
aran@aran-IdeaPad-5-15IIL05:~$ su usuario1
Password: 
suario1@aran-IdeaPad-5-15IIL05:/home/aran$ cd
usuario1@aran-IdeaPad-5-15IIL05:touch archivo1.txt
usuario1@aran-IdeaPad-5-15IIL05:~$ ls -l
-rw-rw-r-- 1 usuario1 usuario1 0 ago  9 21:52 archivo1.txt
usuario1@aran-IdeaPad-5-15IIL05:~$ chmod 640 archivo1.txt
usuario1@aran-IdeaPad-5-15IIL05:~$ ls -l archivo1.txt
-rw-r----- 1 usuario1 usuario1 0 ago  9 21:52 archivo1.txt
usuario1@aran-IdeaPad-5-15IIL05:~$ mkdir directorio1
usuario1@aran-IdeaPad-5-15IIL05:~$ cd directorio1/
usuario1@aran-IdeaPad-5-15IIL05:~/directorio1$ touch archivo2.txt
usuario1@aran-IdeaPad-5-15IIL05:~/directorio1$ ls
archivo2.txt
usuario1@aran-IdeaPad-5-15IIL05:~/directorio1$ chmod u+x archivo2.txt
usuario1@aran-IdeaPad-5-15IIL05:~/directorio1$ 
usuario1@aran-IdeaPad-5-15IIL05:~/directorio1$ ls -l
total 0
-rwxrw-r-- 1 usuario1 usuario1 0 ago  9 22:03 archivo2.txt
usuario1@aran-IdeaPad-5-15IIL05:~/directorio1$ chown :grupo1 archivo2.txt
suario1@aran-IdeaPad-5-15IIL05:~/directorio1$ ls -l
total 0
-rwxrw-r-- 1 usuario1 grupo1 0 ago  9 22:03 archivo2.txt
suario1@aran-IdeaPad-5-15IIL05:~/directorio1$ cd
usuario1@aran-IdeaPad-5-15IIL05:~$ chmod 750 directorio1
usuario1@aran-IdeaPad-5-15IIL05:~$ ls -ld directorio1
drwxr-x--- 2 usuario1 usuario1 4096 ago  9 22:03 directorio1
usuario1@aran-IdeaPad-5-15IIL05:~$ exit
exit
aran@aran-IdeaPad-5-15IIL05:~$ su usuario2
Password: 
usuario2@aran-IdeaPad-5-15IIL05:/home/aran$
aran@aran-IdeaPad-5-15IIL05:~$ su usuario2
Password: 
usuario2@aran-IdeaPad-5-15IIL05:/home/aran$
aran@aran-IdeaPad-5-15IIL05:~$ su usuario2
Password: 
usuario2@aran-IdeaPad-5-15IIL05:/home/aran$
```

- __¿Por qué es importante gestionar correctamente los usuarios y permisos en un sistema operativo?__ .
<br> porque puede ser una buena practica mantener los usuarios con ciertas restricciones, ademas se previenen conflictos entre los usuarios y las aplicaciones que se utilizan para acceso restringido, ademas de esto se pueden trabajar en grupo y organizarse mejor

- ___¿Qué otros comandos o técnicas conocen para gestionar permisos en Linux?__
<br>

ninguno, estoy aprendiendo
