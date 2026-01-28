# ☕ Espresso Tracker PWA

Aplicación web progresiva para registrar y optimizar tus extracciones de espresso.

## Características

- ✅ Registro de shots con todas las variables relevantes
- ✅ Ratio calculado automáticamente
- ✅ Autocompletado basado en entradas anteriores
- ✅ Valores por defecto del último shot
- ✅ Exportación a CSV compatible con Excel
- ✅ Funciona offline
- ✅ Instalable en móvil como app nativa

## Instalación

### Paso 1: Generar los iconos

```bash
pip install cairosvg
python generate_icons.py
```

Si no puedes instalar cairosvg, convierte manualmente el archivo `icons/icon.svg` a PNG en estos tamaños: 72, 96, 128, 144, 152, 192, 384, 512 píxeles.

Puedes usar https://cloudconvert.com/svg-to-png

### Paso 2: Subir a un servidor

La PWA necesita estar alojada en un servidor con HTTPS. Opciones gratuitas:

#### Opción A: GitHub Pages (recomendado)

1. Crea un repositorio en GitHub
2. Sube todos los archivos de esta carpeta
3. Ve a Settings → Pages → Source: "main" branch
4. Tu app estará en `https://tuusuario.github.io/nombre-repo/`

#### Opción B: Netlify

1. Ve a https://netlify.com
2. Arrastra la carpeta completa a "Sites"
3. Obtendrás una URL tipo `https://random-name.netlify.app`

#### Opción C: Vercel

1. Ve a https://vercel.com
2. Importa desde GitHub o sube directamente
3. Obtendrás una URL tipo `https://proyecto.vercel.app`

### Paso 3: Instalar en el móvil

#### iPhone (Safari)
1. Abre la URL de tu app en Safari
2. Toca el botón "Compartir" (cuadrado con flecha)
3. Selecciona "Añadir a pantalla de inicio"
4. Confirma el nombre y toca "Añadir"

#### Android (Chrome)
1. Abre la URL de tu app en Chrome
2. Toca el menú (⋮)
3. Selecciona "Instalar aplicación" o "Añadir a pantalla de inicio"
4. Confirma

## Estructura de archivos

```
espresso-pwa/
├── index.html          # Aplicación principal
├── manifest.json       # Configuración PWA
├── sw.js              # Service Worker (offline)
├── generate_icons.py   # Script para generar iconos
├── README.md          # Este archivo
└── icons/
    ├── icon.svg       # Icono fuente
    ├── icon-72.png    # Iconos generados
    ├── icon-96.png
    ├── icon-128.png
    ├── icon-144.png
    ├── icon-152.png
    ├── icon-192.png
    ├── icon-384.png
    └── icon-512.png
```

## Datos

Los datos se almacenan localmente en tu dispositivo usando `localStorage`. 

- ✅ No se envían a ningún servidor
- ✅ Persisten entre sesiones
- ⚠️ Se pierden si borras datos del navegador
- 💡 Usa "Exportar CSV" regularmente para hacer backup

## Solución de problemas

### La app no se puede instalar
- Asegúrate de usar HTTPS (no HTTP)
- Verifica que todos los iconos existen
- Prueba en Chrome o Safari (Edge y Firefox tienen soporte limitado)

### Los datos no persisten
- Comprueba que no estás en modo incógnito/privado
- Verifica que no tienes bloqueado localStorage

### El service worker no funciona
- El SW solo funciona con HTTPS o localhost
- Comprueba la consola del navegador para errores
