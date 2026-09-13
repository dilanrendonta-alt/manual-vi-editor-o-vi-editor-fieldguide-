# 05 · Buscar y reemplazar

Cuando el archivo es largo, moverse línea por línea deja de ser práctico. Para eso `vi` trae comandos de búsqueda (modo normal) y un comando de sustitución muy potente (modo comando).

## Búsqueda

| Comando | Qué hace | Mi ejemplo |
|---|---|---|
| `/patron` | Busca "patron" hacia adelante desde el cursor | En un archivo de log busco `/error` para saltar directo a la primera aparición de esa palabra. |
| `?patron` | Busca "patron" hacia atrás desde el cursor | Estoy al final del archivo y uso `?TODO` para encontrar la última nota pendiente antes de mi posición. |
| `n` | Repite la última búsqueda en la misma dirección | Después de `/error`, presiono `n` varias veces para saltar a cada siguiente aparición de "error". |
| `N` | Repite la última búsqueda en dirección contraria | Me pasé de la aparición que buscaba; presiono `N` para retroceder a la anterior. |

## Reemplazo con `:%s`

El comando de sustitución sigue el patrón `:[rango]s/viejo/nuevo/[flags]`.

| Comando | Qué hace | Mi ejemplo |
|---|---|---|
| `:%s/viejo/nuevo/g` | Reemplaza **todas** las ocurrencias de "viejo" por "nuevo" en **todo el archivo** | `:%s/localhost/127.0.0.1/g` cambia cada "localhost" por "127.0.0.1" en el archivo completo. |
| `:%s/viejo/nuevo/gc` | Igual que el anterior, pero pide confirmación antes de cada cambio | Uso `:%s/puerto/PUERTO/gc` cuando no estoy seguro de querer cambiar absolutamente todas las apariciones. |
| `:5,10s/viejo/nuevo/g` | Reemplaza solo entre las líneas 5 y 10 | Quiero corregir un nombre de variable pero solo dentro de una función que va de la línea 20 a la 35; uso `:20,35s/viejo/nuevo/g`. |

## Ejercicio para practicar

1. Crea un archivo de práctica con la palabra "hola" repetida en varias líneas: `vi practica_buscar.txt`
2. Busca la palabra con `/hola` y salta entre apariciones con `n` y `N`.
3. Reemplaza todas las apariciones por "adios" con `:%s/hola/adios/g`.
4. Deshaz el cambio con `u` y vuelve a intentarlo, esta vez con `:%s/hola/adios/gc` confirmando uno por uno.
5. Guarda los cambios finales con `:wq`.

---
[⬅ Volver al README](../README.md)