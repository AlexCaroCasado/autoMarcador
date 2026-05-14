# AutoMarcador Studio

Generador automático de resúmenes de partidos con marcadores deportivos superpuestos (VOD). Convierte vídeos crudos de partidos de fútbol base, sala o amateur en resúmenes profesionales en un par de clics, utilizando Python, FastAPI y FFmpeg.

## Características

* **Automatización Total:** Olvídate de editores de vídeo complejos. Sube tu vídeo, adjunta los datos y el servidor hace el resto.
* **Personalización Completa:** Cambia los nombres, escudos (PNG), colores principales y el diseño de la insignia directamente desde una interfaz web moderna.
* **Sincronización Inteligente:** Soporte nativo para segundas partes o prórrogas. Configura en qué minuto y con qué resultado empieza el vídeo.
* **Barra de progreso en tiempo real:** Interfaz responsiva que simula el tiempo estimado de renderizado según la calidad de salida (1080p, 720p, 480p).

---

## Requisitos Previos

Para ejecutar este proyecto de forma local, necesitas tener instalado:

1. **Python 3.9+**
2. **FFmpeg** (El motor de procesamiento de vídeo).

### Instalación de FFmpeg

**Windows:**
1. Ve a [ffmpeg.org](https://www.gyan.dev/ffmpeg/builds/) y descarga la versión *release-essentials* (archivo .zip).
2. Extrae la carpeta y renómbrala a `ffmpeg`. Muévela a tu disco local (Ej: `C:\ffmpeg`).
3. Busca en Windows *"Editar las variables de entorno del sistema"*.
4. En "Variables del sistema", busca **Path** -> Editar -> Nuevo. Añade la ruta a la carpeta bin: `C:\ffmpeg\bin`.
5. Abre una terminal nueva y escribe `ffmpeg -version` para comprobar que funciona.

**Mac / Linux:**
* Mac: `brew install ffmpeg`
* Linux: `sudo apt install ffmpeg`

---

## Instalación del Proyecto

### Opción A: Entorno Local (Python)
1. Clona el repositorio:
   ```bash
   git clone https://github.com/AlexCaroCasado/autoMarcador.git
   cd automarcador

```

2. Instala las dependencias:
```bash
pip install -r requirements.txt

```


3. Ejecuta el servidor:
```bash
uvicorn main:app --reload

```


4. Abre tu navegador en `http://localhost:8000`

### Opción B: Ejecución con Docker

Si no quieres instalar FFmpeg manualmente, levanta el entorno con Docker:

```bash
docker build -t automarcador .
docker run -p 8000:8000 automarcador

```

---

## Cómo usar la herramienta

Para que el programa dibuje los goles en el momento exacto, debes crear un archivo de texto (`.txt`) con los eventos del partido.

El formato debe ser exactamente este por cada línea:
`[Minuto:Segundo] Gol [Equipo (L) o (V)] [Nombre del Jugador]`

**Ejemplo de archivo de texto:**

```text
01:04 Gol (V) Angel
07:41 Gol (L) Grostar
12:53 Gol (L) Pakito
34:30 Gol (V) Angel

```

1. Sube tu vídeo `.mp4`.
2. Sube tu archivo `.txt`.
3. Ajusta los colores y logos en "Personalización".
4. ¡Pulsa renderizar y descarga tu resumen!


## Licencia y Créditos

Este proyecto utiliza **FFmpeg** bajo la licencia LGPLv2.1. FFmpeg es una marca registrada de Fabrice Bellard. Este proyecto no está asociado oficialmente con el proyecto FFmpeg.