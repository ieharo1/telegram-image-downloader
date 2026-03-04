# 🖼️ Telegram Image Downloader PRO

Bot avanzado para descargar imágenes, videos, documentos y cualquier tipo de medio de grupos y canales de Telegram. Desarrollado por **Isaac Esteban Haro Torres**.

---

## 📝 Descripción

Sistema automatizado para respaldo y descarga de contenido multimedia de Telegram. Ideal para crear backups de canales, guardar contenido de grupos, y archivar medios importantes.

### ¿Qué hace este proyecto?

- **Descarga masiva**: Todo tipo de archivos de cualquier chat
- **Filtrado avanzado**: Por tipo, fecha, tamaño, usuario
- **Organización automática**: Estructura de carpetas por chat
- **Respaldo incremental**: Solo descarga contenido nuevo
- **Parallel downloads**: Múltiples descargas simultáneas
- **Resume capability**: Continúa descargas interrumpidas

---

## ✨ Características Principales

| Característica | Descripción |
|----------------|-------------|
| 📥 **Multi-formato** | Imágenes, videos, audio, documentos |
| 🎯 **Filtros precisos** | Por tipo, extensión, tamaño, fecha |
| 📁 **Organización** | Estructura por chat, fecha, tipo |
| ⚡ **Alto rendimiento** | hasta 10 simultáneas |
| descargas 🔄 **Incremental** | Solo baja contenido nuevo |
| 📊 **Reportes** | Logs detallados y estadísticas |

---

## 🛠️ Stack Tecnológico

- **Lenguaje**: Python 3.10+
- **Telegram API**: Telethon (MTProto)
- **Async**: aiohttp, asyncio
- **Archivos**: aiofiles, shutil
- **Organización**: pathlib, os
- **Logging**: Python logging

---

## 🚀 Instalación y Uso

### Instalación

```bash
pip install telethon aiofiles asyncio
```

### Configuración

```python
# config.py
from telethon import TelegramClient

API_ID = 'tu_api_id'      # Obtener en my.telegram.org
API_HASH = 'tu_api_hash'  # Obtener en my.telegram.org

client = TelegramClient('session_name', API_ID, API_HASH)
```

### Uso básico

```python
from teledownloader import TelegramDownloader

downloader = TelegramDownloader(client)

# Descargar de un chat específico
downloader.descargar_chat(
    chat_id='nombre_canal_o_grupo',
    destino='./backups/canal/',
    tipos=['imagen', 'video', 'documento']
)
```

### Descarga avanzada con filtros

```python
# Descarga con filtros específicos
downloader.descargar(
    chat='mi_canal',
    filtros={
        'tipo': ['foto', 'video'],
        'desde': '2025-01-01',
        'hasta': '2025-12-31',
        'tamaño_min': '1MB',
        'tamaño_max': '100MB',
        'usuarios': ['usuario1', 'usuario2']
    },
    paralelo=5,  # 5 descargas simultáneas
    resume=True
)
```

---

## 📁 Estructura de Archivos Descargados

```
backups/
├── Canal_Ejemplo/
│   ├── 2026/
│   │   ├── 01_Enero/
│   │   │   ├── fotos/
│   │   │   │   ├── foto_001.jpg
│   │   │   │   └── video_001.mp4
│   │   │   └── documentos/
│   │   │       └── reporte.pdf
│   │   └── 02_Febrero/
│   └── Grupo_Familiar/
│       └── imagenes/
└── descarga_log.json
```

---

## 📊 Dashboard de Descarga

```
╔═══════════════════════════════════════════════════════╗
║      📥 TELEGRAM MEDIA DOWNLOADER - STATUS            ║
╠═══════════════════════════════════════════════════════╣
║                                                       ║
║  📂 Chat:    Canal de Ejemplo                        ║
║  📦 Estado:  Descargando...                          ║
║                                                       ║
║  Progreso:   ████████████░░░░░░░  65%               ║
║  Archivos:   325 / 500                                ║
║  Tamaño:     2.5 GB                                   ║
║                                                       ║
║  ⏳ Restante: 15 minutos                               ║
║  ⚡ Velocidad: 4.2 MB/s                               ║
║  🔄 Hilos:     5/10 activos                           ║
║                                                       ║
╚═══════════════════════════════════════════════════════╝
```

---

## 💡 Casos de Uso

1. **Backup de canales**: Guarda todo el contenido de tus canales
2. **Archivado de grupos**: Conserva conversaciones importantes
3. **Respaldo multimedia**: Guarda fotos y videos de familia
4. **Auditoría**: Documenta comunicaciones laborales
5. **Análisis**: Prepara datos para procesamiento posterior

---

## 🔧 Opciones de Filtrado

```python
# Filtrar por múltiples criterios
filtros = {
    # Por tipo de archivo
    'tipo': ['foto', 'video', 'documento', 'audio'],
    
    # Por extensión específica
    'extensiones': ['.jpg', '.png', '.mp4', '.pdf'],
    
    # Por fecha
    'desde': '2025-01-01',
    'hasta': '2025-12-31',
    
    # Por tamaño
    'tamaño_min': '500KB',
    'tamaño_max': '50MB',
    
    # Por autor
    'usuarios': ['admin', 'moderador'],
    
    # Palabras clave en caption
    'palabras': ['importante', 'documento', 'factura']
}
```

---

## ⚠️ Notas Importantes

- Necesitas API ID y Hash de my.telegram.org
- Algunos canales privados requieren membresía
- Respeta términos de servicio de Telegram
- No abuses de las descargas paralelas

---

## 🔐 Permisos Requeridos

- `messages.read_history` - Leer historial
- `messages.upload_media` - Descargar medios
- `users.read` - Ver información de usuarios

---

## 🤝 Contribuciones

¿Agregaste soporte para otro tipo de medio?
¡Abre un Pull Request!

---

## 👨‍💻 Desarrollado por Isaac Esteban Haro Torres

**Ingeniero en Sistemas · Full Stack · Automatización · Data**

- 📧 Email: zackharo1@gmail.com
- 📱 WhatsApp: 098805517
- 💻 GitHub: https://github.com/ieharo1
- 🌐 Portafolio: https://ieharo1.github.io/portafolio-isaac.haro/

---

© 2026 Isaac Esteban Haro Torres - Todos los derechos reservados.
