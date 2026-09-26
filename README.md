# Mi Proyecto

Proyecto individual del curso DevOps (TS6D3) de la UTP para practicar el ciclo básico de Git y GitHub: crear un repositorio, versionar cambios, subirlos a GitHub y deshacer errores.

## Instalación

1. Instalar Git y verificar con `git --version`.
2. Clonar el repositorio: `git clone https://github.com/Chavarro09/mi-proyecto-git.git`
3. Entrar a la carpeta: `cd mi-proyecto-git`

## Qué hace cada comando que usé

| Comando | Qué hace, en mis palabras |
|---|---|
| `git init` | Convierte una carpeta normal en un repositorio: crea la carpeta oculta `.git`, donde Git guarda todo el historial. Se usa una sola vez, al empezar. |
| `git status` | Me dice en qué estado están mis archivos: cuáles son nuevos y Git no los sigue (*untracked*), cuáles cambié y cuáles ya están listos para el próximo commit. Lo uso antes y después de cada paso para saber dónde estoy. |
| `git add` | Pasa los cambios de un archivo al área de *staging*, que es como una sala de espera: ahí escojo qué va a entrar en el siguiente commit. |
| `git commit -m "mensaje"` | Guarda una "foto" de lo que está en staging, con un mensaje que explica qué cambió. Cada commit queda en el historial con un código (hash) y se puede volver a él. |
| `git remote add origin <url>` | Conecta mi repositorio local con el repositorio de GitHub y le pone el nombre `origin`. Con `git remote -v` verifico a dónde apunta. |
| `git push` | Sube mis commits locales a GitHub. La primera vez uso `git push -u origin main` para que la rama `main` quede enlazada y después basta con `git push`. |
| `git diff` | Muestra exactamente qué líneas cambié y todavía no he agregado con `git add`: en verde lo que agregué y en rojo lo que quité. Sirve para revisar antes de hacer commit. |
| `git log` | Muestra el historial de commits: autor, fecha, mensaje y hash. Con `git log --oneline --graph` lo veo resumido, un commit por línea. |

### Deshacer cambios

| Comando | Qué hace, en mis palabras |
|---|---|
| `git restore <archivo>` | Descarta los cambios que hice en un archivo y todavía no agregué: lo deja como estaba en el último commit. Ojo: esos cambios se pierden. |
| `git restore --staged <archivo>` | Saca un archivo del staging (deshace el `git add`) pero sin borrar mis cambios: siguen en el archivo. |
| `git reset --soft HEAD~1` | Deshace el último commit pero conserva sus cambios listos en staging, por si me equivoqué en el mensaje o me faltó algo. Lo usé con un commit que todavía no había subido, porque deshacer uno ya subido a GitHub descuadra el historial local con el remoto. |
| `git checkout <hash> -- <archivo>` | Trae un archivo exactamente como estaba en un commit anterior, sin mover el resto del proyecto. |
