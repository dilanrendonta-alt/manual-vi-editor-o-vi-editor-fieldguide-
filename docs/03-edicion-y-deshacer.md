# 03 · Edición y deshacer

Una vez que puedes moverte por el archivo, el siguiente paso natural es poder corregir cosas sin tener que borrar y reescribir todo. Estos comandos, igual que los de navegación, se usan desde **modo normal**.

## Borrar texto

| Comando | Qué hace | Mi ejemplo |
|---|---|---|
| `x` | Borra el carácter bajo el cursor | Escribí "vim" en vez de "vi"; ubico el cursor sobre la "m" y presiono `x` para quitarla. |
| `X` | Borra el carácter antes del cursor | Me pasé un espacio al escribir; presiono `X` para borrar el carácter justo a la izquierda. |
| `dw` | Borra desde el cursor hasta el final de la palabra actual | El cursor está al inicio de "provicional" (mal escrita); presiono `dw` y la reemplazo. |
| `dd` | Borra la línea completa donde está el cursor | Tengo una línea de comentario que ya no sirve; la ubico y presiono `dd` para quitarla entera. |
| `D` | Borra desde el cursor hasta el final de la línea | Quiero conservar el inicio de una línea pero borrar todo lo que sigue; uso `D`. |

## Deshacer y rehacer

| Comando | Qué hace | Mi ejemplo |
|---|---|---|
| `u` | Deshace el último cambio | Borré una línea entera con `dd` por error; presiono `u` y la recupero de inmediato. |
| `Ctrl + r` | Rehace el cambio que acabas de deshacer | Deshice un cambio con `u` pero en realidad sí lo quería; presiono `Ctrl+r` para rehacerlo. |

## Reemplazar y repetir

| Comando | Qué hace | Mi ejemplo |
|---|---|---|
| `r` | Reemplaza un solo carácter sin entrar a modo inserción | Tengo un typo: "ediccion" con doble "c"; ubico el cursor sobre la "c" extra y presiono `r` seguido de la tecla que la reemplaza. |
| `.` | Repite el último cambio realizado | Después de borrar una línea con `dd`, muevo el cursor a otra línea similar y presiono `.` para borrarla también sin volver a escribir el comando. |

## Ejercicio para practicar

1. Crea un archivo de práctica: `vi practica_edicion.txt`
2. Escribe cuatro líneas cualquiera y guarda con `:wq`.
3. Vuelve a abrirlo, borra una palabra con `dw` y una línea completa con `dd`.
4. Presiona `u` dos veces para deshacer ambos cambios.
5. Usa `r` para reemplazar un solo carácter en cualquier línea.
6. Guarda los cambios con `:wq`.

---
[⬅ Volver al README](../README.md)