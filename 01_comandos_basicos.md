

# Comandos Básicos de Git

# Índice

1. [Configuración: `$git config`](#1-configuración-git-config)
2. [Inicialización: `$git init`](#2-inicialización-de-un-repositorio-git-init)

3. [Cambios y guardar versiones: `$git add` y `$git commit`](#3-añadir-cambios-y-guardar-versiones-git-add-y-git-commit)


### 1. Configuración: `$git config`

#### 1.1 Concepto
El comando `git config` permite configurar ajustes de Git a nivel de sistema, usuario o repositorio. Es utilizado para establecer la identidad del usuario y preferencias generales que Git utilizará.

#### 1.2 Comandos más usados

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

#### 1.3 Ejercicio Práctico

- Configura tu nombre y correo en Git utilizando los comandos mencionados anteriormente.
- Verifica la configuración usando `git config --list`.
- Modifica el nombre y el correo, luego comprueba que los cambios se hayan aplicado correctamente.

---

### 2. Inicialización de un repositorio: `$git init`

#### 2.1 Concepto
El comando `git init` se utiliza para crear un nuevo repositorio de Git en el directorio actual. Este comando configura las carpetas y archivos necesarios para comenzar a controlar versiones en el proyecto.

#### 2.2 Comandos más usados

- Inicializar un nuevo repositorio en el directorio actual:

   ```bash
   git init
   ```

- Inicializar un repositorio en una carpeta específica:

   ```bash
   git init <ruta_del_directorio>
   ```

#### 2.3 Ejercicio Práctico

- Crea una nueva carpeta en tu equipo y ejecuta `git init` para convertirla en un repositorio de Git.
- Verifica que el directorio `.git` haya sido creado en la carpeta.

---

### 3. Añadir cambios y guardar versiones: `$git add` y `$git commit`

#### 3.1 Concepto
El comando `git add` añade archivos al área de preparación (staging area), preparándolos para ser confirmados en el historial del repositorio. El comando `git commit` guarda esos cambios en el repositorio.

#### 3.2 Comandos más usados

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

#### 3.3 Ejercicio Práctico

- Crea un archivo nuevo en tu repositorio inicializado.
- Añade el archivo al área de preparación con `git add <nombre_del_archivo>`.
- Confirma los cambios usando `git commit -m "Añadido archivo inicial"`.
- Verifica el historial de commits usando `git log`.
```

