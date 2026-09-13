# ⌨️ Domando a Vi: Manual Práctico del Editor Clásico de Unix

> Una guía paso a paso, con ejercicios y ejemplos propios, para perderle el miedo a `vi` y terminar usándolo con soltura desde cualquier terminal.

![vi](https://img.shields.io/badge/editor-vi-brightgreen)
![Linux](https://img.shields.io/badge/OS-Linux-blue)
![Estado](https://img.shields.io/badge/estado-en%20progreso-yellow)
![Licencia](https://img.shields.io/badge/licencia-MIT-lightgrey)

---

## 📚 Tabla de contenido

- [¿Qué es vi?](#-qué-es-vi)
- [Cheat sheet: comandos esenciales](#️-cheat-sheet-comandos-esenciales)
- [Documentación detallada](#-documentación-detallada)
  - [01 · Instalación y primeros pasos](docs/01-instalacion.md)
  - [02 · Los modos de vi](docs/02-modos-de-vi.md)
  - [03 · Comandos básicos de edición](docs/03-comandos-basicos.md)
  - [04 · Búsqueda y reemplazo](docs/04-busqueda-y-reemplazo.md)
  - [05 · Comandos avanzados](docs/05-comandos-avanzados.md)
  - [06 · Ejercicios prácticos](docs/06-ejercicios-practicos.md)
- [Cómo practicar tú mismo](#-cómo-practicar-tú-mismo)
- [Créditos](#-créditos)



---

## 🤔 ¿Qué es vi?

`vi` (de *visual editor*) es un editor de texto que nació en 1976 dentro del ecosistema Unix, creado por Bill Joy. Es una de esas herramientas que casi se puede dar por garantizada en cualquier sistema Unix o Linux, incluso en las instalaciones más mínimas o en un contenedor recién creado. Su rasgo más particular es que se maneja completamente con el teclado, sin depender de menús ni de mouse, algo que al principio resulta incómodo pero que, con práctica, termina siendo sorprendentemente rápido.

Lo que realmente distingue a `vi` de editores más "amigables" (como nano, gedit o VS Code) es su carácter **modal**: no se comporta igual todo el tiempo, sino que cambia de modo según lo que se quiera hacer. En modo normal, cada tecla se interpreta como un comando (moverse, borrar, copiar), no como texto. Para escribir de verdad hay que pasar a modo inserción, y para guardar o ejecutar operaciones más complejas existe un tercer modo, el modo comando, donde se escriben instrucciones como `:wq`. Este diseño, aunque parezca raro al inicio, evita tener que usar combinaciones incómodas de teclas (como Ctrl+X o Ctrl+C) y permite editar archivos muy rápido sin mover las manos de la fila central del teclado.

Hoy en día existe una versión mejorada y mucho más usada, llamada Vim (*Vi IMproved*), que agrega resaltado de sintaxis, múltiples niveles de deshacer, plugins, entre otras cosas. Pero conocer los fundamentos del `vi` clásico sigue siendo útil porque aparece prácticamente en todas partes: servidores remotos por SSH, contenedores mínimos, sistemas de recuperación, etc. Saber al menos cómo abrir un archivo, editarlo y salir correctamente (sin quedar "atrapado" dentro) es una de esas habilidades básicas que cualquier persona de sistemas o DevOps termina necesitando tarde o temprano.

---

## ⌨️ Cheat sheet: comandos esenciales

| Comando | Qué hace | Mi ejemplo |
|---|---|---|
| `i` | Empieza a insertar texto antes del cursor | Con el cursor sobre la primera letra de una línea, presiono `i` y escribo `Nombre: `, luego `Esc` para volver a normal. |
| `Esc` | Vuelve al modo normal | Después de escribir un párrafo en modo inserción, presiono `Esc` para dejar de insertar. |
| `:wq` | Guarda los cambios y cierra el archivo | Termino de editar `tareas.txt`, escribo `:wq` y el archivo se guarda y vi se cierra. |
| `:q!` | Sale sin guardar cambios | Edité algo por error y quiero descartarlo todo: `:q!` cierra sin tocar el archivo original. |
| `dd` | Borra (corta) la línea completa donde está el cursor | Ubico el cursor en una línea sobrante y presiono `dd` dos veces para borrar dos líneas seguidas. |
| `yy` | Copia (yank) la línea actual | Presiono `yy` sobre una línea de configuración y luego `p` para pegarla justo debajo. |
| `p` | Pega después de la línea o el cursor | Después de un `dd` o `yy`, presiono `p` para pegar el contenido guardado. |
| `x` | Borra un solo carácter bajo el cursor | Corrijo un typo moviendo el cursor sobre la letra sobrante y presionando `x`. |
| `u` | Deshace el último cambio | Borré una línea sin querer con `dd`; presiono `u` y la recupero. |
| `/palabra` | Busca "palabra" hacia adelante en el archivo | Escribo `/error` para saltar directo a la próxima aparición de la palabra "error" en un log. |
| `:%s/viejo/nuevo/g` | Reemplaza todas las ocurrencias en el archivo | `:%s/localhost/127.0.0.1/g` cambia cada "localhost" por "127.0.0.1" en todo el archivo. |
| `gg` / `G` | Va al inicio (`gg`) o al final (`G`) del archivo | En un archivo largo, `gg` me lleva a la primera línea y `G` de un salto a la última. |

---

## 📖 Documentación detallada

Cada tema tiene su propio archivo con explicación y ejercicios dentro de la carpeta [`docs/`](docs/):

1. [Instalación y primeros pasos](docs/01-instalacion.md)
2. [Los modos de vi](docs/02-modos-de-vi.md)
3. [Comandos básicos de edición](docs/03-comandos-basicos.md)
4. [Búsqueda y reemplazo](docs/04-busqueda-y-reemplazo.md)
5. [Comandos avanzados](docs/05-comandos-avanzados.md)
6. [Ejercicios prácticos](docs/06-ejercicios-practicos.md)

---

## 🧪 Cómo practicar tú mismo

### Requisitos
- Una terminal Linux o macOS (en Windows: WSL o Git Bash).
- `vi` o `vim` instalado (casi siempre viene preinstalado; puedes verificarlo con `vi --version`).
- `git` instalado.

### Pasos

```bash
# 1. Clona este repositorio
git clone <URL-de-este-repositorio>

# 2. Entra a la carpeta del proyecto
cd <nombre-del-repositorio>

# 3. Abre cualquier archivo de ejercicios con vi
vi docs/06-ejercicios-practicos.md
```

1. Lee los archivos de `docs/` en orden, empezando por la instalación.
2. Antes de mirar la solución de un ejercicio, intenta resolverlo tú mismo usando solo los comandos de la cheat sheet.
3. Practica sobre una copia de los archivos de ejemplo, no sobre el original, así puedes repetir el ejercicio las veces que quieras:
   ```bash
   cp docs/ejemplos/archivo.txt mi_practica.txt
   vi mi_practica.txt
   ```
4. Cuando te sientas cómodo, intenta hacer una modificación completa (buscar, reemplazar, borrar líneas y guardar) sin salir de `vi` en ningún momento.

---

## 🙌 Créditos

Este manual y sus ejercicios fueron elaborados como parte de una guía de laboratorio académica, tomando como referencia:

- **Guía de laboratorio original:** `manual de uso del editor base de unix VI`
- **Curso:** `seminario de actualizacion 1 . Linux`
- **Docente:** `Bayron Jesit Ospina`
- **Universidad:** Universidad Católica Luis Amigó


