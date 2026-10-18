# T.R Launcher para Android

Versión Android de T.R Launcher. Está construida sobre **Zalith Launcher 2** (código abierto, licencia GPL-3.0)
y usa **el mismo servidor de cuentas** (Cloudflare Worker + D1) que el launcher de PC: las cuentas, los roles y las skins
son los mismos en PC y en el celular.

> **T.R Launcher es una versión modificada NO oficial de Zalith Launcher 2.** No está afiliada al equipo original.
> Se mantienen los avisos de copyright y la licencia GPL-3.0 (ver `LICENSE`). Por la licencia, el código de esta
> versión debe poder consultarse públicamente (por ejemplo, este repositorio en GitHub). Tu servidor y tu base de datos
> NO forman parte del código y siguen siendo privados.

## Qué hace diferente al original

| Función | Cómo funciona |
|---|---|
| **Cuentas T.R** | Botón «Cuenta T.R» al añadir cuenta: crear cuenta o iniciar sesión con el servidor de cuentas. Nombres únicos (no se pueden copiar). La contraseña no se envía: se convierte en el teléfono con scrypt, igual que en PC. |
| **Skins** | Al cambiar la skin se sube al servidor. Antes de abrir el juego se bajan las skins de todos los jugadores para el mod CustomSkinLoader, así todos se ven entre sí en cualquier servidor. |
| **Una sola versión** | Botón «Instalar Minecraft 1.21.11 con Fabric»: instala el juego, Fabric y Fabric API. El mod de skins se baja solo la primera vez. Sin más mods (para evitar problemas en el teléfono). |
| **Servidores** | «Nunca Jamás» y «Nunca Creativo» aparecen como tarjetas en la pantalla principal, con botón de entrada rápida. |
| **Español** | Idioma del juego en español (la primera vez) y paquete de traducciones, igual que en PC. La app ya trae traducción al español. |

## Cómo obtener el APK (sin instalar nada en la PC)

1. Entra en <https://github.com/ZalithLauncher/ZalithLauncher2> con tu cuenta de GitHub y pulsa **Fork** (crea tu copia). Estos archivos están hechos sobre la versión `d2b6545`; si el original cambia mucho más adelante, avísame para actualizarlos.
2. En tu copia, sube los archivos de este paquete respetando las carpetas (**Add file → Upload files**, arrastra las carpetas `.github` y `ZalithLauncher` y el archivo `README_TR_ANDROID.md`).
3. Abre `ZalithLauncher/src/main/java/com/movtery/zalithlauncher/tr/TrConfig.kt`, pulsa el lápiz y pon tu dirección del Worker:
   `const val API_URL = "https://tu-worker.tuusuario.workers.dev"` (la misma de `API_URL` en `src/config.js` de PC). Guarda con **Commit changes**.
   - Alternativa: en **Settings → Secrets and variables → Actions → Variables** crea la variable `TR_API_URL` con esa dirección.
4. Ve a la pestaña **Actions → «Compilar APK de T.R Launcher» → Run workflow**. Tarda entre 15 y 40 minutos.
5. Al terminar, entra en esa ejecución y baja **TR-Launcher-APK** (es un .zip con el `.apk`). Pásalo al celular e instálalo
   (hay que permitir «instalar apps de origen desconocido»).
6. Si la compilación falla, copia el error (texto rojo) y envíamelo: lo corrijo.

## Estado y límites (leer)

- Esta versión se escribió **sin poder compilarla ni probarla en un celular**. Es normal que la primera compilación dé algún
  error pequeño: se corrige con el texto del error.
- Para jugar hace falta un celular con buen procesador y 4 GB de RAM o más. Minecraft 1.21.x en celular depende mucho del equipo.
- El nombre único solo se garantiza dentro de las apps T.R. Si tu servidor está en `online-mode=false`, quien entre con otro
  launcher puede escribir cualquier nombre; la protección real es un plugin tipo AuthMe/EasyAuth o una whitelist.
- La app conserva otras funciones del original (descargar mods, modpacks, etc.). Se pueden ocultar más adelante.
- Desde el menú de cuentas también se puede entrar con Microsoft (cuentas con licencia).
