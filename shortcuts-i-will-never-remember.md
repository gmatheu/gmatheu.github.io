---
layout: page
title: Atajos...
---
...que nunca voy a recordar

---
---
## Bash

`Ctrl-a Ctrl-e` cursor al comienzo/final de línea

`Ctrl-b Ctrl-f` cursor atrás/adelante

`Ctrl-w Ctrl-k` corta el texto del cursor hacia el comienzo o el final.

`Ctrl-u` borra la línea actual.

`Ctrl-y` pega el text cortado luego del cursor.

`Ctrl-d` borra el caracter bajo el cursor

`Ctrl-l` limpia la pantalla.

`Ctrl-r` busca comandos ejecutados

`Ctrl-c` mata el proceso actual.

`Ctrl-z` manda el proceso a segundo plano/suspende

`!! !!<comando>` ejecuta comando anterior o comenzando con <comando>

`^reemplaza^por` reemplaza _reemplaza_ con _por_ en el comando anterior

---
## Tmux

Todos prefijados con __prefix__, en mi caso `Ctrl-B`


`Space` rota los paneles y disposición de los mismos

`Ctrl-o` rota los paneles

---
## Vim

Usando [dot_vim](https://github.com/mutewinter/dot_vim) con `,` como  __Leader__.


`,,` vuelve al archivo anterior.

`,cc ,cb` comentar/Descomentar línea y bloque.

`,hs ,vs` divide el editor horizontal y verticalmente

`Ctrl-w + [h,j,k,l]` Movimiento entre ventanas

`,wo` maximiza la ventana actual

`,sc` cierra ventana

`:bd` cierra buffer actual

`,cm` ejecuta comando en otro panel de Tmux (vía [Vimux](https://github.com/benmills/vimux))

`,w` ejecuta último comando

`,b ,m ,t, u` búsqueda fuzzy en buffers abiertos, archivos MRU, carpeta raíz,
carpeta de archivo actual (vía [Ctr-p](https://github.com/kien/ctrlp.vim))

---
## Sublime

`Ctrl-k + Ctrl-b` esconde/Muestra barra lateral