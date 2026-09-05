# ! Este repositorio fue hecho como parte de un trabajo en la materia de tecnologias en el servidor !

---

# Tarea 2
## Por Alejandro Fernández Arias

## 1. ¿Qué es un sistema de control de versiones?

Un control de versiones es un sistema que registro los cambios realizados en un archivo o conjunto de archivos a lo largo del tiempo, de este modo, pudiendo recuperar versiones anteriores más adelante en el desarrollo. Esto es bastante util en caso de querer comparar cambios entre versiones, verificar quien agrego que, a partir de que version comenzar a verse problemas, etc.

Una de las ventajas que ofrece este sistema es que todos los miembros del equipo de desarrollo saben hasta cierto punto en que estan trabajando los otros miembros del equipo. Tambien como mencionamos anteriormente, el poder rescatar versiones pasadas del proyecto.

---

## 2. ¿Qué es Git?

Git fue creado por Linus Torvalds en 2005. Fue creado durante el desarrollo del kernel de Linux, como el proyecto de habia hecho tan grande requeria de un sistema de control de versiones rapido y eficiente para manejar miles de aportaciones al mismo tiempo.

Que sea un sistema de control de versiones distribuido significa que todos los clientes copian todo el repositorio y no solo un solo archivo, de esta manera, si el servidor central falla, puede ser restaurado desde la copia de cualquiera de los clientes.

---

## 3. Git vs GitHub

### Git

Es la herramienta de control de versiones. Es el sistema como tal, es el que te permite crear los repositorios. 

### GitHub

Es una plataforma que permite almacenar repositorios Git en su propia nube y facilita la colaboración entre desarrolladores permitiendo
el facil acceso a todo el repositorio del proyecto. 

Plataformas similares:

- GitLab: A diferencia de Github se enfoca más en el ciclo completo de DevOps. No se enfoca en el almacenamiento en la nube tampoco,
si no que busca más soportar el self-hosting.

- Bitbucket: Esta creado para ser usado con otros productos de Atlassian como Trello, Jira y Confluence. 
Permite agrupar los repositorios en proyectos y no solo en usuarios u organizaciones como lo hace github.


---

## 4. Instalacion y verificacion de Git

- Sistema operativo utilizado: Windows 11
- Versión de Git instalada: 2.55.0.windows.4
- Comandos utilizado para verificar la instalacion: 

```bash
git --version
```
y
```bash
git config --list
```
---

## 5. Conceptos de Git

- Working Directory: Los archivos en el entorno en el que se estan trabajando.
- Staging Area: Todos los archivos seleccionados para ser incluidos en el commit
- Repository: El historial de commits que ha registrado git para ese proyecto en particular. SOLO contiene aquellos archivos
agregados en los commits
- `git add`: Agrega los archivos del working directory al staging area
- `git commit`: Agrega los archivos del staging area al repositorio

---

## 6. Branches

- ¿Qué es una rama?
Es como un ambiente de desarrollo paralelo, los cambios realizados aqui no afectan a la linea principal del proyecto.

- ¿Por qué un equipo de desarrollo utilizaría ramas?
Para probar nuevo codigo o aislar cambios. Para experimentar sobre el proyecto sin riesgo de alterar la version estable de este.
  
- ¿Qué hace `git merge`? 
Toma el historial de commits y los cambios realizados en una rama para luego integrarlos a la rama en la que estamos.

---

## 7. "Gitignore"

- Para qué sirve `.gitignore`
  
Es un archivo de texto que le indica a git que archivos o carpetas debe ignorar siempre. Cualquier elemento dentro de esa lista no sera identificado por Git ni tampoco podra ser agregado al staging area con git add.
  
- Por qué normalmente no incluimos `node_modules`.
  
No se suele incluir por que suele ser muy grande. Cualquier persona que quiera replicar nuestro node_modules puede hacerlo desde su entorno con un npm install y un package.json.
  
- Por qué un `.env` puede contener información que no debería publicarse.
Generalmente contiene credenciales de acceso lo cual puede poner en riesgo la seguridad del proyecto. Cosas como contraseñas de bases de datos o claves secretas de APIs.

---

## 8. Preguntas de reflexion

1. ¿Qué diferencia existe entre `git add` y `git commit`?
Git add agrega los archivos a la lista de los archivos que el commit eventualmente agregara al repositorio. 
Add agrega al staging area desde del working directory. Commit agrega al repository desde el staging area.

2. ¿Qué ventaja tiene realizar varios commits pequeños en lugar de un solo commit grande?
Es más facil el poder recorrer el historial de esa manera. Por ejemplo, si llega a haber un error, este se puede perder facilmente en un commit grande.
Es más facil identificar que cambio causo el error en varios commits pequeños.

3. ¿Qué diferencia existe entre Git y GitHub?
Git es el sistema de control de versiones, es lo que te permite hacer los repositorios y agregar archivos a el. Github es un servicio que presta servidores para almacenar dichos repositorios, haciendo que estos sean de facil acceso para otros colaboradores.

4. ¿Qué problema resuelven las ramas?
El problema de no poder experimentar con el proyecto sin miedo a romperlo o alterar una version estable de este.

5. ¿Qué información no debería normalmente almacenarse en Git?
Cosas que frenen la reproducibilidad, portabilidad o que contengan informacion sensible como node_modules y .env

6. ¿Qué ocurriría si borras tu proyecto local pero está publicado en GitHub?
Podras bajar la ultima version disponible del proyecto desde GitHub. Cualquier cambio que se tuviera en el local pero no en el remoto desaparecera.

7. ¿Por qué Git es especialmente importante cuando varias personas trabajan sobre el mismo proyecto?
Por que les permite hasta cierto punto tener todos acceso al mismo codigo casi al mismo tiempo.

8. ¿Cuál es la diferencia entre `git clone`, `git pull` y `git push`?
Clone copia el repositorio completo a cierto directorio, pull envia al repositorio local los commits guardados en el repositorio remoto,
push guarda en el repositorio remoto los commits hechos en el repositorio local

9.  ¿Por qué un commit no aparece automáticamente en GitHub?
Por que el commit guarda los cambios en un registro privado y local. Para que github pueda verlos se deben enviar a sus servidor remoto con git push.
