#  Git & GitHub

[![Git](https://img.shields.io/badge/Git-2.37+-f14e32?style=for-the-badge&logo=git&logoColor=white&labelColor=101010)](https://git-scm.com/)
[![GitHub](https://img.shields.io/badge/GitHub-Web-blue?style=for-the-badge&logo=github&logoColor=white&labelColor=101010)](https://github.com/)


Git es un sistema de control de versiones distribuido diseñado para manejar proyectos desde pequeños hasta muy grandes, con rapidez y eficiencia. Fue creado por **Linus Torvalds** en 2005 para el desarrollo del kernel de Linux. A diferencia de otros sistemas de control de versiones, Git es de código abierto y gratuito, lo que lo convierte en una opción popular entre los desarrolladores de todo el mundo.

## Características Clave de Git

- **Control de versiones distribuido**: Cada usuario tiene una copia completa del repositorio, incluyendo su historial. Esto proporciona redundancia y permite operaciones más rápidas.
- **Ramas y fusiones**: Git permite a los usuarios crear ramas para tareas individuales, facilitando el desarrollo en paralelo y la fusión de cambios.
- **Integridad de los datos**: Git asegura la integridad de los datos mediante sumas de verificación, lo que previene la corrupción y proporciona un historial de versiones confiable.
- **Rendimiento**: Git está optimizado para el rendimiento, manejando repositorios pequeños y grandes con facilidad.

Git es especialmente eficaz para gestionar proyectos de software donde están involucrados varios colaboradores, y los cambios deben ser rastreados y gestionados de manera efectiva a lo largo del tiempo.

## Historia detrás del nombre

El término "Git" no tiene un significado específico como acrónimo. En la jerga británica, "git" es un término despectivo que se utiliza para describir a una persona desagradable o incompetente. Linus Torvalds eligió el nombre humorísticamente porque era corto y tenía un significado en el diccionario, lo cual le resultaba divertido.

## ¿Por qué usar Git?

1. **Colaboración**: Git permite que varios desarrolladores trabajen en el mismo proyecto simultáneamente, sin que los cambios entren en conflicto.
2. **Control de versiones**: Con Git, puedes rastrear cada cambio realizado en el proyecto, asegurando que siempre puedas volver a versiones anteriores si es necesario.
3. **Respaldo y restauración**: Dado que cada colaborador tiene una copia completa del repositorio, siempre hay un respaldo disponible.

Visita el sitio oficial de Git [git-scm.com](https://git-scm.com) para más detalles y documentación.

## Conceptos de git

- **working tree o directorio base**: Se refiere al directorio sobre el cual se trabaja con git, abarca desde la carpeta raíz con la carpeta .git, con todos sus archivos y subdirectorio

- **repositorio o repo**: Es un proyecto cualquiera que utilice git

- **rama**: Estados diferentes de un mismo repositorio o proyecto

- **commit**: Se puede entender como un guardado del estado del proyecto en ese momento, es un punto en la historia del proyecto

- **index o staging area**: Es el lugar donde se agregan los cambios que se quieren guardar en el siguiente commit

- **untracked files**: Son los archivos o cambios que git no sigue o de los que no guarda información, estos no estan agregados al index **RECUERDA**: los archivos o cambios que no sigue git no los puedes recuperar si es que los eliminas

- **indexed o staged files**: Archivos o cambios agregados al índice y están listos para hacer un commit, por si ya han utilizado git estos son los archivos o cambios que se agregan cuando se ejecuta el comando `git add`

- **tracked files**: Archivos de los que git ya tiene información, estos archivos tiene commits anteriores y pueden presentar nuevos cambios agregados al index

- **remoto**: Repositorios que están en otro directorio o en otra computadora, github es el mas claro ejemplo de un repositorio remoto, pero tambien se puede tener un repositorio remoto de forma local, solo es un proyecto que esta en un lugar diferente en relación con el repo actual

## Temas
[Instalacións de Git](./00_instalacion.md)

[Comandos Básicos de Git](./01_comandos_basicos.md)
- [Configuración: `$git config`](./01_comandos_basicos.md#1-configuración-git-config)
- [Inicialización: `$git init`](./01_comandos_basicos.md#2-inicialización-de-un-repositorio-git-init)
- [Cambios y guardar versiones: `$git add` y `$git commit`](./01_comandos_basicos.md#3-añadir-cambios-y-guardar-versiones-git-add-y-git-commit)

[Manejo de Ramas en Git](./02_branchs.md)
- [Creación de Ramas](./02_branchs.md#1-creación-de-ramas)
- [Cambio entre Ramas](./02_branchs.md#2-cambio-entre-ramas)
- [Fusión de Ramas](./02_branchs.md#3-fusión-de-ramas)
- [Eliminación de Ramas](./02_branchs.md#4-eliminación-de-ramas)



[Manejo del Historial y Cambios en Git](./03_historial-y-cambios.md)
- [Rebase (Reorganizar el historial)](./03_historial-y-cambios.md#1-rebase-reorganizar-el-historial)
- [Stash (Guardar cambios temporales)](./03_historial-y-cambios.md#2-stash-guardar-cambios-temporales)
- [Reverse (Revertir cambios)](./03_historial-y-cambios.md#3-reverse-revertir-cambios)
- [Reset (Restablecer cambios)](./03_historial-y-cambios.md#4-reset-restablecer-cambios)

[Repositorios Remotos y Resolución de Conflictos](./04_remote-y-conflictos.md)
- [Trabajando con Repositorios Remotos](./04_remote-y-conflictos.md#1-trabajando-con-repositorios-remotos)
- [Resolución de Conflictos](./04_remote-y-conflictos.md#2-resolución-de-conflictos)

### Colaboradores

- [Diego Tapia](https://github.com/juandtap/)
