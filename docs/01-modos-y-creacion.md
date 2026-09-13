# 01 · Modos de vi y creación de archivos

Antes de tocar cualquier comando, lo primero que hay que entender de `vi` es que no es un editor "de un solo modo": según lo que quieras hacer, tienes que estar parado en un modo distinto. Esto es justo lo que más confunde a quien lo usa por primera vez, así que vale la pena detenerse aquí antes de seguir con el resto de la documentación.

## Los tres modos de vi

| Modo | ¿Cómo se activa? | ¿Para qué sirve? |
|---|---|---|
| **Normal** | Es el modo por defecto al abrir vi; se vuelve a él presionando `Esc` desde cualquier otro modo | Moverse por el archivo y ejecutar comandos (borrar, copiar, buscar, etc.). Ninguna tecla escribe texto aquí. |
| **Inserción** | Se activa con `i`, `a`, `o`, entre otros (ver [06 · Insertar texto](06-insertar-texto.md)) | Escribir texto normal, letra por letra, como en cualquier editor de texto. |
| **Comando** (o "de línea") | Se activa escribiendo `:` estando en modo normal | Guardar, salir, buscar y reemplazar, y en general operaciones que afectan todo el archivo o una configuración. |

**Mi ejemplo:** abro un archivo, estoy en modo normal por defecto. Presiono `i` para pasar a inserción y escribo una línea de texto. Presiono `Esc` para volver a normal, y desde ahí escribo `:wq` para guardar y salir. En ese único flujo pasé por los tres modos.

## Crear o abrir un archivo con vi

Para crear un archivo nuevo (o abrir uno existente) basta con pasarle el nombre como argumento:

```bash
vi notas.txt
```

- Si `notas.txt` **no existe**, vi lo crea vacío en memoria; no se guarda en disco hasta que ejecutes `:w` o `:wq`.
- Si `notas.txt` **ya existe**, vi lo abre mostrando su contenido, siempre empezando en modo normal.

**Mi ejemplo:** ejecuto `vi practica.txt` sobre un archivo que no existe todavía. Vi abre una pantalla vacía; escribo un par de líneas en modo inserción y, al guardar con `:wq`, recién ahí se crea `practica.txt` en el directorio actual.

## Ejercicio para practicar

1. Crea un archivo nuevo: `vi mimodos.txt`
2. Presiona `i` y escribe tres líneas cualquiera.
3. Presiona `Esc` para volver a modo normal.
4. Escribe `:wq` para guardar y salir.
5. Verifica que el archivo se creó: `cat mimodos.txt`

---
[⬅ Volver al README](../README.md)