⌨️ Domando a Vi: Manual Práctico del Editor Clásico de Unix

Una guía paso a paso, con ejercicios y ejemplos propios, para perderle el miedo a vi y terminar usándolo con soltura desde cualquier terminal.

Mostrar imagen Mostrar imagen Mostrar imagen Mostrar imagen Mostrar imagen

📚 Tabla de contenido
¿Qué es vi?
Cheat sheet: comandos esenciales
Documentación detallada
01 · Instalación y primeros pasos
02 · Los modos de vi
03 · Comandos básicos de edición
04 · Búsqueda y reemplazo
05 · Comandos avanzados
06 · Ejercicios prácticos
Cómo practicar tú mismo
Créditos


🤔 ¿Qué es vi?

vi (de visual editor) es un editor de texto que nació en 1976 dentro del ecosistema Unix, creado por Bill Joy. Es una de esas herramientas que casi se puede dar por garantizada en cualquier sistema Unix o Linux, incluso en las instalaciones más mínimas o en un contenedor recién creado. Su rasgo más particular es que se maneja completamente con el teclado, sin depender de menús ni de mouse, algo que al principio resulta incómodo pero que, con práctica, termina siendo sorprendentemente rápido.

Lo que realmente distingue a vi de editores más "amigables" (como nano, gedit o VS Code) es su carácter modal: no se comporta igual todo el tiempo, sino que cambia de modo según lo que se quiera hacer. En modo normal, cada tecla se interpreta como un comando (moverse, borrar, copiar), no como texto. Para escribir de verdad hay que pasar a modo inserción, y para guardar o ejecutar operaciones más complejas existe un tercer modo, el modo comando, donde se escriben instrucciones como :wq. Este diseño, aunque parezca raro al inicio, evita tener que usar combinaciones incómodas de teclas (como Ctrl+X o Ctrl+C) y permite editar archivos muy rápido sin mover las manos de la fila central del teclado.

Hoy en día existe una versión mejorada y mucho más usada, llamada Vim (Vi IMproved), que agrega resaltado de sintaxis, múltiples niveles de deshacer, plugins, entre otras cosas. Pero conocer los fundamentos del vi clásico sigue siendo útil porque aparece prácticamente en todas partes: servidores remotos por SSH, contenedores mínimos, sistemas de recuperación, etc. Saber al menos cómo abrir un archivo, editarlo y salir correctamente (sin quedar "atrapado" dentro) es una de esas habilidades básicas que cualquier persona de sistemas o DevOps termina necesitando tarde o temprano.

⌨️ Cheat sheet: comandos esenciales
Comando	Modo	Qué hace	Ejemplo propio
i	Normal → Inserción	Empieza a insertar texto antes del cursor	Con el cursor sobre la primera letra de una línea, presiono i y escribo Nombre: , luego Esc para volver a normal.
Esc	Cualquiera → Normal	Vuelve al modo normal	Después de escribir un párrafo en modo inserción, presiono Esc para dejar de insertar.
:wq	Comando	Guarda los cambios y cierra el archivo	Termino de editar tareas.txt, escribo :wq y el archivo se guarda y vi se cierra.
:q!	Comando	Sale sin guardar cambios	Edité algo por error y quiero descartarlo todo: :q! cierra sin tocar el archivo original.
dd	Normal	Borra (corta) la línea completa donde está el cursor	Ubico el cursor en una línea sobrante y presiono dd dos veces para borrar dos líneas seguidas.
yy	Normal	Copia (yank) la línea actual	Presiono yy sobre una línea de configuración y luego p para pegarla justo debajo.
p	Normal	Pega después de la línea o el cursor	Después de un dd o yy, presiono p para pegar el contenido guardado.
x	Normal	Borra un solo carácter bajo el cursor	Corrijo un typo moviendo el cursor sobre la letra sobrante y presionando x.
u	Normal	Deshace el último cambio	Borré una línea sin querer con dd; presiono u y la recupero.
/palabra	Normal	Busca "palabra" hacia adelante en el archivo	Escribo /error para saltar directo a la próxima aparición de la palabra "error" en un log.
:%s/viejo/nuevo/g	Comando	Reemplaza todas las ocurrencias en el archivo	:%s/localhost/127.0.0.1/g cambia cada "localhost" por "127.0.0.1" en todo el archivo.
gg / G	Normal	Va al inicio (gg) o al final (G) del archivo	En un archivo largo, gg me lleva a la primera línea y G de un salto a la última.
📖 Documentación detallada

Cada tema tiene su propio archivo con explicación y ejercicios dentro de la carpeta docs/:

Instalación y primeros pasos
Los modos de vi
Comandos básicos de edición
Búsqueda y reemplazo
Comandos avanzados
Ejercicios prácticos
🧪 Cómo practicar tú mismo
Requisitos
Una terminal Linux o macOS (en Windows: WSL o Git Bash).
vi o vim instalado (casi siempre viene preinstalado; puedes verificarlo con vi --version).
git instalado.
Pasos
bash
# 1. Clona este repositorio
git clone <URL-de-este-repositorio>

# 2. Entra a la carpeta del proyecto
cd <nombre-del-repositorio>

# 3. Abre cualquier archivo de ejercicios con vi
vi docs/06-ejercicios-practicos.md
Lee los archivos de docs/ en orden, empezando por la instalación.
Antes de mirar la solución de un ejercicio, intenta resolverlo tú mismo usando solo los comandos de la cheat sheet.
Practica sobre una copia de los archivos de ejemplo, no sobre el original, así puedes repetir el ejercicio las veces que quieras:
bash
   cp docs/ejemplos/archivo.txt mi_practica.txt
   vi mi_practica.txt
Cuando te sientas cómodo, intenta hacer una modificación completa (buscar, reemplazar, borrar líneas y guardar) sin salir de vi en ningún momento.
🙌 Créditos

Este manual y sus ejercicios fueron elaborados como parte de una guía de laboratorio académica, tomando como referencia:

Guía de laboratorio original: Manual del Editor VI 
Curso: Linux
Docente: Bayron Ospina 
Universidad: Universidad Católica Luis Amigó


