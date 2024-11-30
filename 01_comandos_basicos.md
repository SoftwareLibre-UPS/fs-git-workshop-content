

# Comandos Básicos de Git

# Índice

1. [Configuración: `$git config`](#1-configuración-git-config)
2. [Inicialización: `$git init`](#2-inicialización-de-un-repositorio-git-init)

3. [Cambios y guardar versiones: `$git add` y `$git commit`](#3-añadir-cambios-y-guardar-versiones-git-add-y-git-commit)


## 1. Configuración: `$git config`

### 1.1 Concepto
El comando `git config` permite configurar ajustes de Git a nivel de sistema, usuario o repositorio. Es utilizado para establecer la identidad del usuario y preferencias generales que Git utilizará.

Git permite dos tipos de configuración:
- **Local**: específica para cada repositorio.
- **Global**: aplicada por defecto a todos los repositorios del usuario.

La configuración local puede diferir de la global. A continuación se detalla cómo configurar Git desde la terminal, cómo acceder a la configuración global y cómo asignar un nombre de usuario y correo electrónico.

#### Archivos de Configuración Global

Dependiendo del sistema operativo, el archivo de configuración global se encuentra en distintas ubicaciones:
- **Linux**: `~/.gitconfig`
- **Windows**: `C:\Users\<nombre-de-usuario>\.gitconfig`
- **MacOS**: (Buscar ruta específica)

---
### Comandos de Configuración

- **Ver la configuración**:

   ```bash
   git config --list                # Muestra toda la configuración
   git config --global --list       # Muestra solo la configuración global
   git config list --global         # Nueva forma de mostrar la configuración global
   ```

- **Verificar un valor específico**:

   ```bash
   git config --global <seccion>.<llave>
   git config --global --get <seccion>.<llave>
   git config get --global <seccion>.<llave>  # Nueva forma
   ```

   **Ejemplo**:
   ```bash
   git config --global rerere.enabled
   # Salida esperada:
   > true
   ```

- **Borrar un valor**:

   ```bash
   git config --global --unset <seccion>.<llave>          # Forma deprecada
   git config unset --global rerere.enabled               # Nueva forma
   ```

   **Nota**: el archivo rerere (**re**use **re**corded **re**solution) facilitar la gestión de conflictos en fusiones (merges) al recordar cómo resolviste un conflicto específico y aplicar automáticamente esa resolución si el mismo conflicto ocurre nuevamente en el futuro

   **Ejemplo**:
   ```bash
   git config --local --unset rerere.enabled
   git config unset --global rerere.enabled
   ```

- **Agregar valores**:

   ```bash
   git config --global --add <seccion>.<llave> <valor>    # Forma deprecada
   git config set --local <seccion>.<llave> <valor>       # Nueva forma
   ```

### 1.2 Comandos más usados

- Configuración del nombre de usuario:

   ```bash
   git config --global user.name "<nombre>"
   ```

- Configuración del correo electrónico del usuario:

   ```bash
   git config --global user.email "<email>"
   ```

- Verificación de la configuración actual:

   ```bash
   git config --list
   ```

   - **`--global`**: Aplica la configuración a nivel de usuario (global).
   - **`--system`**: Configura Git a nivel de todo el sistema.
   - **`--local`**: Aplica los ajustes solo en el repositorio actual.



### 1.3 Ejercicio Práctico - Configuración de Git (Global)





> Verifica la configuración de Git. Si no tienes asignado el nombre de usuario y correo electrónico, agrégalos ahora.

- Para agregar el nombre de usuario y correo electrónico globalmente:

   ```bash
   git config --global --add user.name "<tu-nombre-de-usuario>"
   git config --global --add user.email "<tu-correo-personal>"
   ```

- **Verificar la configuración**:

   Comprueba que los valores se hayan configurado correctamente con `git config --global --list`.

     ```bash
   git config --global --list`
   ```



---

## 2. Inicialización de un repositorio: `$git init`

### 2.1 Concepto
El comando `git init` se utiliza para crear un nuevo repositorio de Git en el directorio actual. Este comando configura las carpetas y archivos necesarios para comenzar a controlar versiones en el proyecto.

### 2.2 Comandos más usados

- Inicializar un nuevo repositorio en el directorio actual:

   ```bash
   git init
   ```

- Inicializar un repositorio en una carpeta específica:

   ```bash
   git init <ruta_del_directorio>
   ```
- Iniciar con otra rama principal
    ```bash
   git init -b <nombre-rama>
   git init --initial-branch=<nombre-rama>
   ```
   Ejemplo

         git init -b trunk
         git init -b master
         git init -b main


### 2.3 Ejercicio Práctico

- Crea una nueva carpeta en tu equipo y ejecuta `git init` para convertirla en un repositorio de Git.

   ```bash
   git init -b main
   ```

- Verifica que el directorio `.git` haya sido creado en la carpeta.


---


## 3. Añadir cambios y guardar versiones: `$git add` y `$git commit`

### 3.1 Concepto
El comando `git add` añade archivos al área de preparación (staging area), preparándolos para ser confirmados en el historial del repositorio. El comando `git commit` guarda esos cambios en el repositorio.

#### Visualizar el Historial de Commits

Revisar el historial de commits es útil para conocer los cambios realizados y quién los hizo.

1. **Ver el historial completo de commits**:

   ```bash
   git log
   ```

2. **Ver un historial compacto**:

   ```bash
   git log --oneline
   ```

3. **Ver el historial en formato gráfico**:

   ```bash
   git log --graph
   ```

   También puedes combinar ambos:

   ```bash
   git log --oneline --graph
   ```

Estos comandos muestran los commits realizados, la fecha y hora, y el nombre de quien realizó los cambios.

> **Conceptos Importantes**:
> - **HEAD**: Refleja el commit en el que estás actualmente.
> - **HASH del Commit**: Es el identificador único de cada commit.
> - **git blame**: Muestra el historial de cambios por línea, permitiendo ver quién hizo cada cambio.


### 3.2 Comandos más usados

- Añadir un archivo específico al área de preparación:

   ```bash
   git add <nombre_del_archivo>
   ```

- Añadir todos los archivos modificados al área de preparación:

   ```bash
   git add .
   ```

- Confirmar (commit) los cambios en el repositorio con un mensaje descriptivo:

   ```bash
   git commit -m "Descripción de los cambios"
   ```

- Confirmar todos los cambios con una descripción interactiva:

   ```bash
   git commit
   ```

- Listar los commits realizados:

   ```bash
   git log --oneline
   ```

### 3.3 Ejercicio Práctico

- Crea un archivo nuevo en tu repositorio inicializado.
- Añade el archivo al área de preparación con `git add <nombre_del_archivo>`.
- Confirma los cambios usando `git commit -m "Añadido archivo inicial"`.
- Verifica el historial de commits usando `git log`.


### 3.3 Ejercicio Práctico - Agregar Archivos y Guardar Cambios

Para esta práctica, trabajaremos con archivos Markdown para mayor simplicidad, pero ten en cuenta que estos comandos aplican para cualquier tipo de archivo y directorio.

### Agregar Archivos al Repositorio

1. **Crear un archivo** `archivo_1.md` y agregar texto usando cualquier editor.
2. **Ver el estado del repositorio**:
   
   ```bash
   git status
   ```
   
   Verás que el archivo aparece como "no rastreado" (untracked), lo que significa que aún no forma parte del repositorio.

3. **Agregar el archivo al área de preparación (staging area)**:

   - Para agregar un archivo específico:
     
     ```bash
     git add archivo_1.md
     ```

   - Para agregar todos los archivos en el directorio actual:

     ```bash
     git add .
     ```

   - Para agregar archivos por tipo o extensión usando expresiones regulares:

     ```bash
     git add *.md                # Agrega todos los archivos con extensión .md
     git add carpeta/*.txt        # Agrega todos los archivos .txt dentro de la carpeta "carpeta"
     ```

      


#### Primer Commit

El comando `git commit` permite registrar los cambios agregados al área de preparación en el historial del repositorio. Es obligatorio acompañarlo de un mensaje breve y descriptivo sobre los cambios.

1. **Realizar un commit con mensaje**:

   ```bash
   git commit -m "Add: file archivo_1.md has been added"
   ```

   Esto crea un "punto de guardado" en el repositorio con el mensaje que describiste.

2. **Agregar texto adicional y verificar el estado**:

   - Agrega más texto al archivo `archivo_1.md`.
   - Ejecuta `git status` nuevamente para ver la diferencia con el archivo antes del cambio.

3. **Commit Rápido para Archivos Modificados**:

   Para agregar y hacer commit de todos los archivos modificados directamente:

   ```bash
   git commit -am "Add: file archivo_1.md has been added"
   ```

   > **Consejo**: Evita realizar commits por cada pequeño cambio, ya que esto puede llenar el historial de commits y dificultar la revisión de cambios cuando surgen problemas en el proyecto.



