
# Manejo del Historial y Cambios en Git

# Índice

1. [Rebase (Reorganizar el historial)](#1-rebase-reorganizar-el-historial)
2. [Stash (Guardar cambios temporales)](#2-stash-guardar-cambios-temporales)
3. [Reverse (Revertir cambios)](#3-reverse-revertir-cambios)
4. [Reset (Restablecer cambios)](#4-reset-restablecer-cambios)

---

## 1. Rebase (Reorganizar el historial)

### 1.1 Concepto
El comando `git rebase` reorganiza el historial de commits moviendo una rama a otra base. Es útil para mantener un historial más limpio y lineal, evitando "commits de merge" en exceso. 

### 1.2 Comandos más usados

- **Rebase interactivo**:

   ```bash
   git rebase -i <base>
   ```

   - **`-i`**: Modo interactivo para editar, combinar, o reordenar commits.

- **Rebase de una rama**:

   ```bash
   git checkout <rama>
   git rebase <base>
   ```

- **Cancelar un rebase en progreso**:

   ```bash
   git rebase --abort
   ```

### 1.3 Ejercicio Práctico

1. Crea una nueva rama `rebase-demo` y realiza dos commits:

   ```bash
   git checkout -b rebase-demo
   echo "Primer commit" > rebase1.txt
   git add rebase1.txt
   git commit -m "Add: Primer commit en rebase-demo"
   
   echo "Segundo commit" > rebase2.txt
   git add rebase2.txt
   git commit -m "Add: Segundo commit en rebase-demo"
   ```

2. Cambia a la rama principal y realiza un commit en `main`:

   ```bash
   git checkout main
   echo "Commit en main" > main.txt
   git add main.txt
   git commit -m "Add: Cambios en main"
   ```

3. Vuelve a la rama `rebase-demo` y haz un rebase contra `main`:

   ```bash
   git checkout rebase-demo
   git rebase main
   ```

4. Revisa el historial para confirmar el rebase:

   ```bash
   git log --oneline
   ```

---

## 2. Stash (Guardar cambios temporales)

### 2.1 Concepto
El comando `git stash` guarda los cambios en un área temporal, permitiendo trabajar en otra tarea sin perder el progreso actual.

### 2.2 Comandos más usados

- **Guardar cambios en el stash**:

   ```bash
   git stash
   ```

- **Aplicar el stash más reciente**:

   ```bash
   git stash apply
   ```

- **Listar los stashes almacenados**:

   ```bash
   git stash list
   ```

- **Eliminar el stash más reciente**:

   ```bash
   git stash drop
   ```

### 2.3 Ejercicio Práctico

1. Realiza un cambio sin hacer commit y guárdalo en el stash:

   ```bash
   echo "Cambio temporal" > temporal.txt
   git add temporal.txt
   git stash
   ```

2. Cambia a la rama `main` y revisa que el cambio ya no está:

   ```bash
   git checkout main
   ```

3. Vuelve a aplicar el stash y haz un commit:

   ```bash
   git stash apply
   git commit -m "Add: Cambio temporal recuperado"
   ```

---

## 3. Reverse (Revertir cambios)

### 3.1 Concepto
El comando `git revert` permite deshacer un cambio de un commit específico, creando un nuevo commit que lo anula. Es ideal para revertir cambios en un entorno compartido.

### 3.2 Comandos más usados

- **Revertir un commit específico**:

   ```bash
   git revert <hash-del-commit>
   ```

- **Revertir múltiples commits (interactivo)**:

   ```bash
   git revert -n <hash1> <hash2>
   ```

### 3.3 Ejercicio Práctico

1. Haz un commit con un cambio erróneo:

   ```bash
   echo "Cambio erróneo" > error.txt
   git add error.txt
   git commit -m "Add: Cambio erróneo"
   ```

2. Reviértelo con `git revert`:

   ```bash
   git revert <hash-del-commit-erróneo>
   ```

3. Verifica que el nuevo commit anula el cambio:

   ```bash
   git log --oneline
   ```

---

## 4. Reset (Restablecer cambios)

### 4.1 Concepto
El comando `git reset` restablece cambios en el historial de commits o en el área de trabajo. Dependiendo del modo utilizado, puede descartar cambios o eliminar commits.

### 4.2 Comandos más usados

- **Restablecer al último commit (hard reset)**:

   ```bash
   git reset --hard
   ```

- **Mover el HEAD sin alterar el área de trabajo (soft reset)**:

   ```bash
   git reset --soft <hash>
   ```

- **Descartar cambios en el área de trabajo**:

   ```bash
   git reset HEAD <archivo>
   ```

### 4.3 Ejercicio Práctico

1. Haz un commit y restablécelo con `--soft`:

   ```bash
   echo "Cambio temporal para reset" > reset.txt
   git add reset.txt
   git commit -m "Add: Cambios para reset"
   git reset --soft HEAD~1
   ```

2. Observa que los cambios siguen en el área de preparación (`staging`).

3. Realiza un hard reset:

   ```bash
   git reset --hard
   ```

4. Verifica que los cambios se han eliminado.

