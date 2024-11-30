# Trabajando con Repositorios Remotos y Resolución de Conflictos

# Índice

1. [Trabajando con Repositorios Remotos](#1-trabajando-con-repositorios-remotos)
2. [Resolución de Conflictos](#2-resolución-de-conflictos)

---

## 1. Trabajando con Repositorios Remotos

### 1.1 Concepto
Un repositorio remoto es una copia de tu repositorio local que está alojada en un servidor externo (como GitHub, GitLab, o Bitbucket). Estos repositorios permiten la colaboración entre desarrolladores y sirven como respaldo del proyecto.

### 1.2 Comandos más usados

- **Agregar un repositorio remoto**:

   ```bash
   git remote add origin <url-del-repositorio>
   ```

- **Ver los repositorios remotos configurados**:

   ```bash
   git remote -v
   ```

- **Actualizar tu repositorio local con cambios remotos**:

   ```bash
   git fetch origin
   git pull origin <rama>
   ```

   - **`fetch`**: Obtiene los cambios sin aplicarlos automáticamente.
   - **`pull`**: Obtiene y aplica los cambios directamente.

- **Enviar cambios locales al remoto**:

   ```bash
   git push origin <rama>
   ```

   - **`-u`**: Configura la rama actual para rastrear la rama remota.

### 1.3 Ejercicio Práctico

1. **Configurar un repositorio remoto**:
   - Crea un repositorio nuevo en GitHub y copia la URL HTTPS o SSH.
   - Enlázalo con tu repositorio local:

     ```bash
     git remote add origin <url-del-repositorio>
     ```

2. **Subir tu proyecto a GitHub**:
   - Asegúrate de que el proyecto tiene commits.
   - Sube los cambios:

     ```bash
     git push -u origin main
     ```

3. **Actualizar cambios desde el remoto**:
   - Realiza un cambio en GitHub (por ejemplo, edita un archivo desde la web).
   - Actualiza tu repositorio local:

     ```bash
     git pull origin main
     ```

---

## 2. Resolución de Conflictos

### 2.1 Concepto
Un conflicto ocurre cuando Git no puede fusionar automáticamente los cambios de dos ramas, ya sea al hacer un merge o un pull. Esto sucede cuando ambos cambios afectan las mismas líneas de un archivo.

### 2.2 Comandos más usados

- **Detectar conflictos**:

   Al intentar un `merge` o `pull`, Git notificará si hay conflictos.

   ```bash
   git merge <rama>
   ```

- **Ver archivos en conflicto**:

   ```bash
   git status
   ```

- **Resolver un conflicto manualmente**:
   - Edita el archivo para mantener los cambios deseados.
   - Marca el conflicto como resuelto:

     ```bash
     git add <archivo-en-conflicto>
     ```

- **Completar el proceso de fusión**:

   ```bash
   git commit
   ```

- **Cancelar la fusión en progreso** (si no deseas continuar):

   ```bash
   git merge --abort
   ```

### 2.3 Ejercicio Práctico

1. **Crear un conflicto**:
   - Desde la rama `main`, crea un archivo y haz un commit:

     ```bash
     echo "Contenido en main" > conflicto.txt
     git add conflicto.txt
     git commit -m "Add: contenido en main"
     ```

   - Cambia a una nueva rama `conflicto-demo` y edita el mismo archivo:

     ```bash
     git checkout -b conflicto-demo
     echo "Contenido en conflicto-demo" > conflicto.txt
     git add conflicto.txt
     git commit -m "Edit: contenido en conflicto-demo"
     ```

   - Vuelve a `main` e intenta fusionar `conflicto-demo`:

     ```bash
     git checkout main
     git merge conflicto-demo
     ```

2. **Resolver el conflicto**:
   - Edita el archivo `conflicto.txt` y elige qué cambios conservar.
   - Marca el conflicto como resuelto:

     ```bash
     git add conflicto.txt
     ```

3. **Completar la fusión**:

   ```bash
   git commit -m "Resolve: conflicto en conflicto.txt"
   ```

4. **Verificar el resultado**:
   - Revisa que el archivo `conflicto.txt` contenga los cambios esperados.
   - Confirma que el historial refleja el merge:

     ```bash
     git log --oneline --graph
     ```
