# 🎤 Pininfarina Karaoke Console Player

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.7+-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/Platform-Windows%20%7C%20macOS%20%7C%20Linux-4EAA25?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Status-Working-brightgreen?style=for-the-badge" />
</p>

<p align="center">
  <b>🎵 Karaoke ASCII Art en consola para "Pininfarina (Remix)"</b><br>
  <i>Rei · Neo Pistea · DUKI</i>
</p>

---

## ✨ Características

- 🔤 **ASCII Art Grande** — Cada palabra se revela en arte ASCII y se acumula visualmente
- 🎵 **Sincronización precisa** — Basada en timestamps del archivo `.lrc`, tú controlas la velocidad
- 🎨 **Colores dinámicos** — Paleta rotativa por cada línea de la canción
- 📊 **Barra de progreso** — Tiempo transcurrido y total en tiempo real
- 👀 **Preview de próximas líneas** — Anticipa lo que viene
- 🔄 **Reemplazo inteligente** — Una sola línea visible a la vez, sin scroll infinito
- 🐢 **Velocidad configurable** — Control total desde el `.lrc`: lento, rápido, o como quieras

---

## 📦 Herramientas utilizadas

| Herramienta | Uso | Instalación |
|------------|-----|------------|
| **Python 3.7+** | Lenguaje principal del script | [python.org](https://python.org) |
| **pyfiglet** | Genera ASCII art a partir de texto | `pip install pyfiglet` |
| **ffmpeg / ffplay** | Reproduce audio sincronizado | [ffmpeg.org](https://ffmpeg.org) o `winget install Gyan.FFmpeg` |
| **pygame** (alternativa) | Reproduce audio cross-platform | `pip install pygame` |
| **Bloc de notas / VS Code** | Editar timestamps del `.lrc` | Incluido en Windows / [code.visualstudio.com](https://code.visualstudio.com) |
| **CMD / PowerShell** | Ejecutar el script | Incluido en Windows |

---

## 🚀 Instalación paso a paso

### Paso 1: Instalar Python
1. Ve a [python.org/downloads](https://python.org/downloads)
2. Descarga Python 3.7 o superior
3. ⚠️ **IMPORTANTE**: En la instalación, marca ✅ **"Add Python to PATH"**
4. Click en "Install Now"
5. Verifica que quedó bien:
```bash
python --version
```

### Paso 2: Instalar pyfiglet
```bash
pip install pyfiglet
```

### Paso 3: Instalar un reproductor de audio (elige uno)

#### 🔹 Opción A: ffmpeg (recomendado, más preciso)
1. Ve a [gyan.dev/ffmpeg/builds](https://gyan.dev/ffmpeg/builds)
2. Descarga `ffmpeg-release-essentials.zip`
3. Descomprime y copia la carpeta `bin` a `C:\ffmpeg\bin`
4. Agrega `C:\ffmpeg\bin` al PATH de Windows:
   - `Win + R` → `sysdm.cpl` → "Variables de entorno"
   - En "Path" → "Editar" → "Nuevo" → `C:\ffmpeg\bin`
5. Verifica:
```bash
ffplay -version
```

#### 🔹 Opción B: pygame (más fácil, sin PATH)
```bash
pip install pygame
```

### Paso 4: Descargar los archivos del proyecto
Descarga estos 3 archivos y ponlos en la misma carpeta:
```
📁 pininfarina-karaoke/
├── 🎤 karaoke.py
├── 📝 pininfarina.lrc
└── 🎵 pininfarina.mp3   ← añade tu audio aquí
```

---

## 🎮 Uso

### Opción 1: Auto-detectar (más fácil)
Abre PowerShell o CMD en la carpeta del proyecto y ejecuta:
```bash
python karaoke.py
```
> El script detecta automáticamente el `.lrc` y el `.mp3`.

### Opción 2: Especificar archivos
```bash
python karaoke.py pininfarina.lrc pininfarina.mp3
```

### Durante la reproducción
| Tecla | Acción |
|-------|--------|
| `ENTER` | Iniciar el karaoke (después del splash) |
| `Ctrl+C` | Salir en cualquier momento |

---

## 🎶 Sobre la canción: "Pininfarina (Remix)"

> *"Móntate que yo sé lo que tú quieres, girl / Pininfarina, diseño y diseño"*

🏎️ **Pininfarina** es una histórica carrozzeria italiana fundada en 1930, responsable de diseñar algunos de los autos más icónicos del mundo: Ferrari, Alfa Romeo, Maserati, y el mítico Ferrari Testarossa.

En el contexto del trap argentino, la palabra se convirtió en sinónimo de **lujo, estatus y diseño impecable**. La canción es una oda a la opulencia, al estilo de vida que muchos artistas urbanos alcanzan después de años de *grind*.

---

## 👤 Artistas

| Artista | Rol | Info |
|---------|-----|------|
| **Rei** | Artista original | De Morón, Buenos Aires. Pasó del freestyle en plazas a firmar con Dale Play Records. "Pininfarina" fue su carta de presentación al mainstream en 2020. |
| **Neo Pistea** | Remix | Pionero del trap argentino, miembro de Modo Diablo junto a Duki y Ysy A. Referente del sonido oscuro y melódico del género. |
| **DUKI** | Remix | El artista urbano argentino más grande de la historia. Llevó el trap argentino a estadios y colaboró con internacionales como Bad Bunny y Quevedo. |

### 🏆 Por qué "Pininfarina" significó tanto
- **Para Duki**: Antes de este remix, estaba en un momento crítico: sus fans se estaban aburriendo de flows repetitivos. Este tema llegó en el momento exacto para reafirmar su dominio en el trap latino, demostrando que podía adaptarse a cualquier estilo y seguir siendo el rey.
- **Para Rei**: Fue la puerta de entrada al mainstream — pasar de freestyle underground a tener a los dos pesos pesados del género en su tema.

> *"Esto e un palo pa la historia"* 🏆

---

## 🛠️ Personalizar velocidad

La velocidad se controla **100% desde el archivo `.lrc`**. No hay límites internos en el script.

### Abrir el archivo
```bash
# Windows
notepad pininfarina.lrc

# O con VS Code
code pininfarina.lrc
```

### Formato de timestamps
```
[mm:ss.xx] Texto de la canción
```

| Parte | Significado | Rango |
|-------|-------------|-------|
| `mm` | Minutos | 00-99 |
| `ss` | Segundos | 00-59 |
| `xx` | Centésimas de segundo | 00-99 |

### Ejemplo: hacer una parte más lenta
```lrc
[03:26.50]Muchas noches en Miami, ah
[03:31.50]          ← +5 segundos después
[03:36.00]          ← +4.5 segundos más
[03:40.00]          ← +4 segundos más
[03:44.00]          ← +4 segundos más
[03:52.00]Cien mil por cada show, sigo pegándome
```
> **Regla**: Cuanto más separados estén los timestamps, más lento va. Cuanto más juntos, más rápido.

### Ejemplo: deletreo letra por letra (como "F-e-r-r-a-r-i")
```lrc
[03:52.00]F
[03:52.35]e
[03:52.70]r
[03:53.05]r
[03:53.40]a
[03:53.75]r
[03:54.10]i,
[03:54.80]Ferrari
```
> Cada letra es una línea separada. El script las muestra una por una en ASCII art grande.

### 💡 Truco: líneas vacías para pausas
```lrc
[03:26.50]Muchas noches en Miami, ah
[03:31.50]          ← línea vacía = pausa de 5 segundos
[03:52.00]Cien mil por cada show...
```
> Una línea con timestamp pero sin texto crea una pausa visual.

---

## 📁 Estructura del proyecto

```
📁 pininfarina-karaoke/
├── 🎤 karaoke.py          # Script principal (Python)
├── 📝 pininfarina.lrc     # Letra con timestamps sincronizados
├── 🎵 pininfarina.mp3     # Audio (añade el tuyo)
└── 📖 README.md           # Este archivo
```

---

## 🖥️ Vista previa

```
        ♫  K A R A O K E  ♫
        ──────────────────────────

        ┌────────────────────────┐
        │  ██████╗  ███████╗    │
        │  ██╔══██╗ ██╔════╝    │
        │  ██████╔╝ █████╗      │
        │  ██╔═══╝  ██╔══╝      │
        │  ██║      ███████╗    │
        │  ╚═╝      ╚══════╝    │
        └────────────────────────┘

           F e r r a r i

        ──────────────────────────
        1. Móntate en el carro...
        2. Ellos hablan tanto...

        [━━━━━●────────────────] 35.2%
        01:32 / 04:21
```

---

## 🙏 Créditos

| | |
|---|---|
| **Letra y música** | Rei, Neo Pistea, DUKI |
| **Karaoke console player** | Basado en [lyricsuwu](https://github.com/antonyayansi/lyricsuwu) de Antony Ayansi |
| **ASCII Art** | [pyfiglet](https://github.com/pwaller/pyfiglet) |
| **Herramientas** | Python, ffmpeg, VS Code, PowerShell |

---

<p align="center">
  <b>Hecho con 💜 por <a href="https://github.com/ElizabethCarinaLavillaPillco">@ElizabethCarinaLavillaPillco</a></b><br>
  <i>🏎️ Móntate en el carro, ponte la chaqueta, shorty 🏎️</i>
</p>
