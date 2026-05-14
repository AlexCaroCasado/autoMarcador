# ⚽ AutoMarcador Studio

Generador automático de resúmenes de partidos con marcadores deportivos superpuestos. Da un toque más estético a partidos de fútbol base, sala o amateur en un par de clics, utilizando Python, FastAPI y FFmpeg.

## Características

* **Automatización Total:** Olvídate de editores de vídeo complejos. Sube tu vídeo, adjunta los datos y el servidor hace el resto.
* **Personalización Completa:** Cambia los nombres, escudos (PNG), colores principales y el diseño de la insignia directamente desde una interfaz web.
* **Sincronización Inteligente:** Soporte nativo para segundas partes o prórrogas. Configura en qué minuto y con qué resultado empieza el vídeo.

---

## 📋 Requisitos Previos

Para ejecutar este proyecto de forma local, necesitas tener instalado:

1. **Python 3.9+**
2. **FFmpeg** (El motor de procesamiento de vídeo).

## 🚀 Instalación del Proyecto

1. Clonar el repositorio:
```bash
git clone https://github.com/AlexCaroCasado/autoMarcador.git
cd autoMarcador
```

### Opción A: Ejecución con Docker (Recomendada)

Esta es la vía más rápida y segura, ya que el contenedor incluye FFmpeg preinstalado y configurado automáticamente.

```bash
docker build -t automarcador .
docker run -p 8000:8000 automarcador
```
Abre tu navegador en `http://localhost:8000`

### Opción B: Entorno Local (Python)

Nota: Si utilizas esta opción, debes asegurarte de tener FFmpeg instalado manualmente en tu sistema y añadido a las Variables de Entorno (PATH).

1. Instala las dependencias:
```bash
pip install -r requirements.txt
```

2. Ejecuta el servidor:
```bash
uvicorn main:app --reload
```

3. Abre tu navegador en `http://localhost:8000`

---

## 📖 Cómo usar la herramienta

Para que el programa dibuje los goles en el momento exacto, debes crear un archivo de texto (`.txt`) con los eventos del partido.

El formato debe ser exactamente este por cada línea:
`[Minuto:Segundo] Gol [Equipo (L) o (V)] [Nombre del Jugador]`

**Ejemplo de archivo de texto:**

```text
01:04 Gol (V) Fran
07:41 Gol (L) Pablo
12:53 Gol (L) Dani
34:30 Gol (V) Fran
```

1. Sube tu vídeo `.mp4`.
2. Sube tu archivo `.txt`.
3. Ajusta los colores y logos en "Personalización".
4. ¡Pulsa renderizar y descarga tu resumen!


## Licencia y Créditos

Este proyecto utiliza **FFmpeg** bajo la licencia LGPLv2.1. FFmpeg es una marca registrada de Fabrice Bellard. Este proyecto no está asociado oficialmente con el proyecto FFmpeg.