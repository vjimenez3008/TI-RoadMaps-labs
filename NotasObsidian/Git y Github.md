
### 🧭 **Tabla de comandos Git esenciales (orden lógico de uso)**

|🧩 Orden|🖥️ Comando|💬 Descripción breve|📍 Cuándo usarlo|
|---|---|---|---|
|1|`git init`|Inicializa un nuevo repositorio Git en la carpeta actual.|Solo si el proyecto aún no tiene repositorio `.git`.|
|2|`git status`|Muestra el estado del repositorio (archivos nuevos, modificados, eliminados, etc.).|Para verificar qué archivos están listos o pendientes de subir.|
|3|`git add .`|Agrega **todos los archivos** nuevos o modificados al área de preparación (_staging_).|Cada vez que quieres incluir cambios en un commit.|
|4|`git commit -m "mensaje"`|Crea un **commit** (una versión guardada) con los archivos agregados.|Después de `git add`, antes de hacer `push`.|
|5|`git branch`|Muestra las ramas locales y la actual (marcada con `*`).|Para saber en qué rama estás trabajando.|
|6|`git checkout -b nombre-rama`|Crea una nueva rama y te cambia a ella.|Si deseas crear una rama nueva localmente.|
|7|`git checkout nombre-rama`|Cambia entre ramas existentes.|Para moverte entre ramas (por ejemplo, `main` ↔ `clases-magistrales`).|
|8|`git remote add origin <URL>`|Conecta tu repositorio local a un repositorio remoto en GitHub.|Solo una vez, al vincular tu proyecto local con GitHub.|
|9|`git branch -u origin/<rama>`|Configura la rama local para seguir una rama remota.|Si tu rama local no está sincronizada con la remota.|
|10|`git push -u origin <rama>`|Sube la rama actual al repositorio remoto y la vincula.|La primera vez que subes una nueva rama a GitHub.|
|11|`git push`|Sube tus commits locales al repositorio remoto.|Cada vez que haces nuevos commits.|
|12|`git pull`|Descarga los últimos cambios del repositorio remoto.|Antes de trabajar o para sincronizar con GitHub.|
|13|`git ls-files`|Muestra los archivos rastreados por Git.|Para verificar qué archivos están bajo control de versiones.|
|14|`git log --oneline --graph`|Muestra el historial de commits de forma resumida y visual.|Para revisar los commits realizados.|
|15|`git rm --cached <archivo>`|Quita un archivo del seguimiento de Git, sin borrarlo físicamente.|Si agregaste por error algo que no quieres subir.|
|16|`git restore <archivo>`|Restaura un archivo modificado a su última versión confirmada.|Para revertir cambios locales.|
|17|`Move-Item <origen> <destino>` _(PowerShell)_|Mueve carpetas o archivos en tu sistema.|Para mover tu carpeta `quiniela` dentro del repositorio correcto.|
|18|`dir` _(PowerShell)_|Lista los archivos y carpetas del directorio actual.|Para verificar estructura de carpetas antes de subir.|
|19|`pwd` _(PowerShell)_|Muestra la ruta actual donde estás ubicado.|Para confirmar que estás dentro del repositorio.|
|20|`git clone <URL>`|Descarga un repositorio remoto a tu equipo.|Si quieres obtener una copia desde GitHub.|

---

### 🧾 **Flujo típico para subir un proyecto a GitHub (resumen ordenado)**

1️⃣ Ir al proyecto local  
`cd C:\Repositorio-GIT\2025-3-PrograAvanzada`

2️⃣ Inicializar (solo si no tiene `.git`)  
`git init`

3️⃣ Conectar a GitHub  
`git remote add origin https://github.com/vjimenez3008/2025-3-Programacion-Avanzada.git`

4️⃣ Crear o moverte a la rama correcta  
`git checkout -b clases-magistrales`  
(o si ya existe: `git checkout clases-magistrales`)

5️⃣ Agregar archivos  
`git add .`

6️⃣ Crear el commit  
`git commit -m "Agregar proyecto Quiniela"`

7️⃣ Subir los cambios  
`git push -u origin clases-magistrales`

8️⃣ Verificar en GitHub (rama `clases-magistrales`)  
👉 [https://github.com/vjimenez3008/2025-3-Programacion-Avanzada](https://github.com/vjimenez3008/2025-3-Programacion-Avanzada)