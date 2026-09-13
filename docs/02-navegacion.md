# 02 · Navegación básica y saltos

Como en `vi` no hay mouse, moverse rápido por el archivo depende completamente de conocer los comandos de navegación. Todos estos comandos se usan en **modo normal**.

## Movimiento carácter a carácter

| Comando | Qué hace | Mi ejemplo |
|---|---|---|
| `h` | Mueve el cursor una columna a la izquierda | Estoy a mitad de una línea larga y presiono `h` varias veces para retroceder hasta el inicio de una palabra. |
| `l` | Mueve el cursor una columna a la derecha | Después de corregir un carácter con `x`, presiono `l` para avanzar antes de seguir editando. |
| `j` | Mueve el cursor una línea hacia abajo | Reviso un archivo de configuración línea por línea presionando `j` repetidamente. |
| `k` | Mueve el cursor una línea hacia arriba | Me pasé de línea buscando un valor y presiono `k` para regresar. |

## Movimiento por palabras y líneas

| Comando | Qué hace | Mi ejemplo |
|---|---|---|
| `w` | Salta al inicio de la siguiente palabra | En una línea con varias variables, uso `w` para saltar de una a otra sin leer letra por letra. |
| `b` | Salta al inicio de la palabra anterior | Me pasé de una palabra y uso `b` para regresar a su inicio sin usar `h` varias veces. |
| `0` | Va al primer carácter de la línea (columna 0) | Estoy al final de una línea larga y presiono `0` para volver de un salto al principio. |
| `$` | Va al último carácter de la línea | Quiero agregar algo al final de una línea larga; presiono `$` y luego `a` para insertar ahí. |

## Saltos dentro del archivo completo

| Comando | Qué hace | Mi ejemplo |
|---|---|---|
| `gg` | Va a la primera línea del archivo | En un archivo de log largo, presiono `gg` para ir directo al inicio. |
| `G` | Va a la última línea del archivo | Uso `G` para saltar al final de un archivo y ver la entrada más reciente de un log. |
| `:N` | Va directamente a la línea número `N` | Un compilador me marca un error en la línea 42; escribo `:42` y caigo justo ahí. |

## Ejercicio para practicar

1. Abre cualquier archivo con varias líneas: `vi docs/01-modos-y-creacion.md`
2. Usa `gg` para ir al inicio y `G` para ir al final.
3. Desde el final, usa `k` cinco veces para subir cinco líneas.
4. Usa `0` y luego `$` en esa línea para moverte entre su inicio y su fin.
5. Escribe `:10` (o el número de línea que exista en tu archivo) y confirma que el cursor saltó ahí.

---
[⬅ Volver al README](../README.md)