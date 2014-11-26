---
layout: page
title: Comandos...
---
...que nunca voy a recordar

---
---
## Git

`git branch --merged | xargs git branch -d` Borrar branches no mergeados
`git revert -m 1 <sha-1-del-merge>` Revertir merge
`git clone --depth X URL` Clona limitando la cantidad de historia

---
## Memcached

Ejecutando `echo <cmd> | nc localhost 11211` o vía __telnet__

`flush_all` Borrar todo

`stats items` muestra estadísticas del contenido

`stats cachedump 1 100`


---
## Telnet

`Ctrl-AltGr-] Ctrl-Shift-] + Enter` Salir!!!


---
## Redis

Accediendo via __telnet__ o __redis-cli__

`FLUSHALL` Borra todo el contenido

`MONITOR` Arranca el monitor


---
## Otros

`cat /proc/<PID>/cmdline`
> Muestra comando usado para lanzar procso

`proxytunnel -p proxy-server:3128 -d www.google.com:443 -a 7000`
> Tunel al host usando un proxy y levanta un cliente en el puerto 7000

`openssl s_client -connect localhost:7000 -ssl3`
> conecta al servidor usando la versión de SSL/TLS configurada

`netstat -lnp` procesos con conexiones abiertas

`lsof -i TCP` procesos que abrieron puertos TCP

`fc` abre el último comando en el editor y al guardar lo ejecuta

`fc -nl -1` muestra último comando

`strace`
> Muestra las __system calls__ (man 2) que ejecuta un comando o proceso

`ldd`
> Muestra dependencias de librerías (shared libraries)

`info`
> Ayuda de comandos. Similar a __man__
