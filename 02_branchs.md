
# Manejo de Ramas en Git

# Índice

1. [Creación de Ramas](#1-creación-de-ramas)
2. [Cambio entre Ramas](#2-cambio-entre-ramas)
3. [Fusión de Ramas](#3-fusión-de-ramas)
4. [Eliminación de Ramas](#4-eliminación-de-ramas)

---

## 1. Creación de Ramas

### 1.1 Concepto
En Git, las ramas permiten desarrollar características, realizar pruebas o trabajar en correcciones de errores de manera aislada. Cada rama representa una línea de tiempo de desarrollo independiente, lo que facilita la colaboración y el desarrollo paralelo.

### 1.2 Comandos más usados

- **Crear una rama** sin cambiar a ella:

   ```bash
   git branch <nombre-de-la-rama>
   ```

- **Crear y cambiar a una nueva rama**:

   ```bash
   git checkout -b <nombre-de-la-rama>
   ```

   - **`-b`**: Crea y cambia a la nueva rama.

### 1.3 Ejercicio Práctico

1. Crea una nueva rama llamada `archivo_2.md` y cámbiala de inmediato:

   ```bash
   git checkout -b dev
   ```

2. En esta nueva rama, crea un archivo `login.md` y agrega texto de ejemplo:

   ```bash
   echo "Funcionalidad de creada en desarrollo" > archivo_2.md
   git add archivo_2.md
   git commit -m "Add: file archivo_2.md"
   ```

---

## 2. Cambio entre Ramas

### 2.1 Concepto
El cambio entre ramas en Git permite moverse de una línea de desarrollo a otra. Este proceso es útil para revisar cambios en diferentes partes del proyecto o para trabajar en varias características a la vez.

### 2.2 Comandos más usados

- **Ver la lista de ramas** en el repositorio:

   ```bash
   git branch
   ```

- **Cambiar a otra rama existente**:

   ```bash
   git checkout <nombre-de-la-rama>
   ```

### 2.3 Ejercicio Práctico

1. Verifica las ramas disponibles en tu repositorio con `git branch`.
    ```bash
    git branch
    ```
2. Cambia a la rama `main` (o según el nombre de tu rama principal):

   ```bash
   git checkout main
   ```

3. Observa el contenido del repositorio y nota que no verás los cambios realizados en `archivo_2.md`. Este archivo no deberia existir.

4. Volvemos ala rama `dev`

    ```bash
    git checkout dev
    ```

---

## 3. Fusión de Ramas

### 3.1 Concepto
La fusión (merge) de ramas permite combinar cambios de una rama en otra. Este proceso es común al incorporar una rama de características en la rama principal, consolidando todo el trabajo en una sola línea de desarrollo.

### 3.2 Comandos más usados

- **Fusionar cambios de una rama en la rama activa**:

   ```bash
   git merge <nombre-de-la-rama>
   ```

   - Este comando fusiona `<nombre-de-la-rama>` en la rama en la que estás actualmente.

### 3.3 Ejercicio Práctico

1. Cambia a la rama `main` y fusiona los cambios de la rama dev `dev`:

   ```bash
   git checkout main
   git merge dev
   ```

2. Revisa el historial de commits para confirmar que los cambios de `archivo_2.md` ahora están en `main`:

   ```bash
   git log --oneline
   ```

---

## 4. Eliminación de Ramas

### 4.1 Concepto
Una vez que los cambios de una rama han sido fusionados o si ya no es necesaria, la rama puede eliminarse. Esto ayuda a mantener el repositorio limpio y organizado.

### 4.2 Comandos más usados

- **Eliminar una rama fusionada**:

   ```bash
   git branch -d <nombre-de-la-rama>
   ```

- **Eliminar una rama sin fusionar** (forzado):

   ```bash
   git branch -D <nombre-de-la-rama>
   ```

### 4.3 Ejercicio Práctico

1. Elimina la rama `archivo_2.md` después de verificar que ha sido fusionada en `main`:

   ```bash
   git branch -d dev
   ```

2. Revisa la lista de ramas para asegurarte de que `dev` ha sido eliminada:

   ```bash
   git branch
   ```

