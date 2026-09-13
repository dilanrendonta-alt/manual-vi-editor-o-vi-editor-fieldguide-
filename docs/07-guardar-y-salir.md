# 07 · Guardar y salir

Este es el último punto de la documentación y, curiosamente, el que más problemas causa a quien usa `vi` por primera vez: la razón por la que tanta gente termina buscando "cómo salir de vim" desesperada. Aquí quedan todas las formas de guardar y cerrar, todas ejecutadas desde **modo comando** (con `:`), salvo una excepción.

## Guardar y salir

| Comando | Qué hace | Mi ejemplo |
|---|---|---|
| `:w` | Guarda los cambios sin salir | Llevo un rato editando y quiero guardar un punto de control sin cerrar el archivo; escribo `:w`. |
| `:w nombre.txt` | Guarda una copia con otro nombre | Estoy probando cambios sobre `config.txt` pero no quiero sobrescribir el original; uso `:w config_prueba.txt`. |
| `:wq` | Guarda los cambios y cierra | Terminé de editar `tareas.txt`; escribo `:wq` y el archivo se guarda y vi se cierra en un solo paso. |
| `:x` | Igual que `:wq`, pero solo guarda si hubo cambios reales | Abrí un archivo solo para revisarlo y no cambié nada; uso `:x` en vez de `:wq` (aunque en la práctica el resultado es el mismo si no hay cambios). |
| `ZZ` | Atajo en modo normal (sin `:`) equivalente a `:wq` | En vez de escribir dos puntos, desde modo normal presiono `ZZ` para guardar y salir más rápido. |
| `:q` | Sale del archivo, pero **solo si no hay cambios sin guardar** | Abrí un archivo solo para leerlo y no escribí nada; `:q` cierra sin problema. |
| `:q!` | Sale **forzado**, descartando cualquier cambio sin guardar | Edité varias líneas por error y no quiero conservarlas; `:q!` cierra sin guardar nada de lo hecho. |

## Ejercicio para practicar

1. Abre un archivo de práctica: `vi practica_salir.txt`
2. Escribe una línea y guarda sin salir con `:w`.
3. Escribe una segunda línea y guarda una copia con otro nombre: `:w practica_salir_copia.txt`
4. Vuelve al archivo original, escribe una tercera línea y ciérralo con `:wq`.
5. Ábrelo de nuevo, escribe algo que no quieras conservar y ciérralo sin guardar con `:q!`.
6. Verifica con `cat practica_salir.txt` que ese último cambio no quedó guardado.

## Resumen final

Con esto se completan las siete categorías de comandos de este manual: modos y creación, navegación, edición y deshacer, copiar y pegar, buscar y reemplazar, insertar texto, y guardar y salir. La [cheat sheet del README principal](../README.md#️-cheat-sheet-comandos-esenciales) reúne los comandos más usados de todas estas secciones en una sola tabla de referencia rápida.

---
[⬅ Volver al README](../README.md)