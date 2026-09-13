# 04 · Copiar y pegar

En `vi` copiar se llama "yank" (de ahí que el comando sea `y`), y pegar se llama "put". No hay portapapeles visible ni `Ctrl+C`/`Ctrl+V`: todo se hace con combinaciones cortas en modo normal.

## Copiar (yank)

| Comando | Qué hace | Mi ejemplo |
|---|---|---|
| `yy` | Copia la línea completa donde está el cursor | Tengo una línea de configuración que se repite más abajo; la copio con `yy` para no reescribirla. |
| `yw` | Copia desde el cursor hasta el final de la palabra actual | Quiero reutilizar solo el nombre de una variable sin copiar el resto de la línea; ubico el cursor al inicio y uso `yw`. |
| `3yy` | Copia la línea actual más las dos siguientes (en general, `Nyy` copia N líneas) | Necesito duplicar un bloque de tres líneas de un archivo de configuración; uso `3yy` y luego pego el bloque completo. |

## Pegar (put)

| Comando | Qué hace | Mi ejemplo |
|---|---|---|
| `p` | Pega el contenido copiado **después** de la línea o el cursor | Después de `yy` sobre una línea, muevo el cursor una línea más abajo y presiono `p` para pegarla justo ahí. |
| `P` | Pega el contenido copiado **antes** de la línea o el cursor | Copié una línea con `yy` y quiero que la copia quede arriba de la original, no abajo; uso `P` en vez de `p`. |

## Ejercicio para practicar

1. Abre un archivo con al menos tres líneas: `vi practica_copiar.txt`
2. Ubica el cursor en la primera línea y cópiala con `yy`.
3. Baja al final del archivo y pégala con `p`.
4. Ubica el cursor al inicio de una palabra y cópiala con `yw`.
5. Muévete a otra línea y pégala ahí con `p`.
6. Prueba la diferencia entre `p` y `P` pegando la misma copia dos veces, una con cada comando.

---
[⬅ Volver al README](../README.md)