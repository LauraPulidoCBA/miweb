**Git**, un **sistema de control de versiones** (VCS, por sus siglas en inglés), es una herramienta indispensable y obligatoria para todo programador.

Git es el **sistema distribuido de control de versiones más popular** a nivel mundial. Es una herramienta fundamental para desarrolladores, siendo necesario aprenderlo para conseguir un trabajo. Git permite tener un historial completo del código de una aplicación. Su principal ventaja es que permite realizar un *roll back* (volver atrás) a una versión anterior sin errores, lo cual es vital cuando se trabaja con un equipo grande y se introducen fallos involuntariamente.

Git trabaja de **manera descentralizada**. A diferencia de los sistemas centralizados, cada desarrollador tiene una copia completa del código, lo que permite seguir trabajando incluso si el servidor central falla.

**Definición**
Git es un software que permite llevar un historial detallado de los cambios realizados en un proyecto de software, similar a un diario que registra la vida de la aplicación, incluyendo corrección de errores, adición de funciones y versiones. Fue creado por Linus Torvalds (creador del kernel de Linux) en 2005.

**Beneficios y Usos Clave:**

Git proporciona un historial completo del trabajo realizado, permite almacenar código en la nube, facilita el trabajo en equipo, y ayuda a **identificar exactamente cuándo se introdujo un error** en la aplicación revisando el historial de *commits*.

**Características Clave**
Git es el sistema de control de versiones más utilizado porque es **distribuido**. Esto significa que cada desarrollador tiene una copia idéntica (**clon**) del repositorio en su equipo local, permitiéndoles trabajar sin necesidad de conexión a un servidor central o a internet. Esta distribución también asegura que cada desarrollador tenga un *backup* del proyecto.

Las **ramas**. Las ramas son bifurcaciones o nuevos caminos que toma el proyecto, permitiendo trabajar en un ambiente aislado (por ejemplo, para una nueva característica o una corrección) sin comprometer el proyecto principal (la rama **master**). Una vez terminado el trabajo, la rama se **fusiona** (*merge*) con la principal.

**Terminología Esencial**
*   **Repositorio (Repository):** Todo proyecto cuyo historial está siendo seguido por Git.
*   **Commit (Cómic):** Cada cambio registrado en el historial de Git.
*   **Clon (Clone):** Una copia exacta del repositorio. Es lo primero que un programador debe hacer al unirse a un equipo.
*   **Fork:** Un proyecto completamente diferente creado a partir de otro.

**Flujo de Trabajo Básico**
El flujo básico de trabajo con Git implica tres áreas: el área de trabajo, el **área de preparación** (*staging area*), y el repositorio.

1.  El desarrollador crea o clona el repositorio (usando `git init` o `git clone`).
2.  Los cambios se añaden al área de preparación usando `git add`.
3.  Una vez seguro de los cambios, estos se registran de forma definitiva en el historial con `git commit` y un mensaje que explica la modificación.

**Trabajo en Equipo**
En un equipo, se suelen usar dos ramas principales: **master** (protegida, donde está la versión de producción) y **dev**. Los desarrolladores sacan sus propias ramas de *dev* para trabajar. El trabajo completado se integra primero en *dev* mediante una fusión (*merge*), asegurando que no haya conflictos, y solo después *dev* se integra en *master* para mandar a producción.

**Herramientas**
Aunque existen clientes gráficos, es indispensable aprender Git a través de la **terminal o línea de comandos** (usando comandos como `push`, `pull` y `merge`) para entender su funcionamiento.

Para equipos distribuidos, se usan **repositorios en la nube** (ramas remotas) alojados en plataformas como **GitHub**, **Bitbucket**, y **GitLab**. Es importante recordar que **Git** es la tecnología subyacente, mientras que **GitHub** es una de las empresas que ofrece el servicio de alojamiento de repositorios en la nube.

**Configuración e Instalación**

Uso de la **terminal**. Se recomienda a los usuarios de Windows utilizar **Git Bash** (que emula comandos de Linux o Mac), y **no** la terminal de Windows CMD, para evitar problemas.

La configuración inicial de Git incluye establecer de forma global (`--global`):
1.  El nombre del usuario (`user.name`).
2.  El correo electrónico (`user.email`).
3.  El editor de texto predeterminado (por ejemplo, VS Code, utilizando la opción `--wait`).

Una configuración crítica es `core.autocrlf` para manejar los saltos de línea. Debe configurarse a `true` en Windows, y a `input` en Linux o Mac.


**Flujo de Trabajo (Workflow) Básico**

El flujo de trabajo central de Git implica tres etapas principales:
1.  **Directorio de Trabajo:** Donde se agregan o modifican archivos.
2.  **Staging Area (Área de Preparación):** Se usa el comando **`git add`** para seleccionar los cambios que se desean guardar. Esto es una etapa intermedia para verificar antes de comprometer.
3.  **Repositorio (Commit):** Se usa **`git commit`** para guardar o "comprometer" los cambios seleccionados, registrándolos en el historial. Los *commits* deben llevar un mensaje que tenga sentido.

Otros comandos esenciales son:
*   **`git init`**: Inicializa un repositorio Git vacío.
*   **`git status`**: Muestra el estado actual del repositorio, indicando archivos no seguidos (*untracked*) o modificados. Se recomienda usar `git status -s` para una vista corta y elegante.
*   **`git log --oneline`**: Muestra el historial de *commits* de manera resumida.
*   **`.gitignore`**: Un archivo que lista rutas o nombres de archivos (como `.env` o `node_modules`) que Git debe ignorar para que no se suban al repositorio.
*   **`git diff`**: Permite ver los cambios que no se han pasado al *staging*.

**Ramas (Branching) y Fusión (Merging)**

Las ramas permiten que los desarrolladores trabajen en nuevas funcionalidades de forma independiente a la rama principal (*main*).
*   **`git checkout -b <nombre_rama>`**: Crea una nueva rama y se cambia a ella.
*   **`git branch`**: Muestra la rama actual.
*   **`git merge <nombre_rama>`**: Trae los cambios de una rama secundaria a la rama principal (se debe estar en la rama de destino, por ejemplo, *main*, antes de ejecutar el comando).

**Trabajo Remoto con GitHub**

Para subir el código a la nube (como GitHub), se deben seguir estos pasos:
1.  Crear el repositorio en la plataforma remota.
2.  Vincular el repositorio local con el servidor remoto usando **`git remote add origin <url>`**.
3.  Subir los cambios con **`git push -u origin main`**.

Al subir cambios a GitHub, en lugar de usar la contraseña de registro, se requiere generar un **Personal Access Token (PAT)** para la autenticación. Una vez configurado el repositorio remoto, se usa `git push` después de cada *commit* para sincronizar los cambios.
