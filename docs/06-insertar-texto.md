# 06 · Insertar texto

En [01 · Modos y creación de archivos](01-modos-y-creacion.md) vimos que `i` entra a modo inserción. Pero `vi` tiene varias formas de entrar a ese modo, y cada una empieza a escribir en un punto distinto de la línea. Elegir la correcta ahorra varios movimientos de cursor.

## Formas de entrar a modo inserción

| Comando | Qué hace | Mi ejemplo |
|---|---|---|
| `i` | Inserta texto **antes** del cursor | El cursor está sobre la "m" de "edicion"; presiono `i` y escribo la letra que faltaba justo ahí. |
| `a` | Inserta texto **después** del cursor | Quiero agregar una letra justo después de donde está el cursor, sin moverme; uso `a` en vez de `i` y ahorro un `l`. |
| `I` | Inserta al **inicio** de la línea, sin importar dónde esté el cursor | El cursor está a mitad de la línea y quiero agregar un comentario `# ` al principio; uso `I` para saltar directo ahí. |
| `A` | Inserta al **final** de la línea, sin importar dónde esté el cursor | Quiero agregar un punto y coma al final de una línea larga; uso `A` en vez de navegar con `$`. |
| `o` | Abre una **línea nueva debajo** y entra a inserción ahí | Estoy en medio de una lista y quiero agregar un elemento nuevo después del actual; uso `o`. |
| `O` | Abre una **línea nueva arriba** y entra a inserción ahí | Se me olvidó un encabezado antes de un bloque; uso `O` para crear la línea justo arriba sin cortar nada. |

## Ejercicio para practicar

1. Abre un archivo de práctica: `vi practica_insertar.txt`
2. Escribe una línea de texto y presiona `Esc`.
3. Usa `A` para ir al final de esa línea y agregar más texto.
4. Usa `I` para ir al inicio de la misma línea y agregar un prefijo.
5. Usa `o` para crear una línea nueva debajo con otro texto.
6. Usa `O` sobre esa última línea para crear una línea nueva arriba de ella.
7. Guarda los cambios con `:wq`.

---
[⬅ Volver al README](../README.md)