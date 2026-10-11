# 💥 Comic-AI - Generative AI Comic & Manga Creator Studio

**Comic-AI** is a full-stack creative web studio powered by **Django** and **Stable Diffusion** (`ogkalu/Comic-Diffusion`). Designed for artists, storytellers, and creators, it enables generating, styling, and laying out original comic strips and manga pages in an interactive canvas editor.

---

## 🌟 Key Features

- **Dual Generative Styles**:
  - 🦸 **Western Comic Book Style**: Bold ink contours, dynamic cel shading, colorful dramatic lighting, and vintage halftone printing textures.
  - ⛩️ **Japanese Manga Style**: Clean black & white line art, authentic screentone shading, expressive anime eyes, and dramatic angles.
- **Interactive Comic Page Canvas**:
  - Drag-and-drop panel arranger with customizable resolution presets (512x512 and higher).
  - 16+ speech bubble and thought balloon designs.
  - 15+ action impact effects (burst lines, shockwaves, explosion stars).
  - Halftone overlay patterns for retro print aesthetics.
- **Extensive Typography Library**:
  - Over 20 bundled comic and manga display fonts (ActionComics, Badaboom, Komikax, AnimeAce, SuperComic, etc.).
- **Story Persistence & Export**:
  - Save multi-panel pages to local SQLite storage with `PageContent` database models.
  - Dedicated page viewer for reading and sharing completed comic stories.

---

## 🛠️ Tech Stack

- **Backend**: Python 3.10+, Django 5.x
- **AI & Deep Learning Engine**:
  - PyTorch (CUDA acceleration)
  - Hugging Face Diffusers (`DiffusionPipeline`)
  - Transformers & Accelerate
  - Model: Pretrained `ogkalu/Comic-Diffusion`
- **Image Processing**: PIL / Pillow, Base64 JSON streaming
- **Database**: SQLite3 (Django ORM)
- **Frontend**: HTML5, Modern CSS3 Canvas, Vanilla JavaScript

---

## 📁 Repository Structure

```text
comic-ai/
└── comic_ai/
    ├── manage.py               # Django CLI management script
    ├── comic_ai/               # Project configuration & settings
    │   ├── settings.py
    │   ├── urls.py
    │   └── wsgi.py
    ├── main/                   # Core application
    │   ├── models.py           # PageContent database schema
    │   ├── views.py            # AI diffusion endpoints (comic & manga) & save handlers
    │   ├── urls.py             # Route definitions
    │   └── templates/          # Home, Comic Creator, Manga Creator & Viewer templates
    └── static/                 # Creative static assets
        ├── src/messageboxes/   # 16+ comic dialogue & thought bubble variants
        ├── src/effects/        # 15+ action effects & impact stars
        ├── src/halftone/       # Retro comic halftone dot textures
        ├── src/texts/          # 20+ comic & manga fonts (.ttf / .otf)
        └── comic.css           # Studio canvas stylesheet
```

---

## 🚀 Getting Started

### Prerequisites

- Python 3.10 or higher
- Nvidia GPU with CUDA support (strongly recommended for fast image generation)

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/CGhost1908/comic-ai.git
   cd comic-ai/comic_ai
   ```

2. **Create and activate a virtual environment:**
   ```bash
   python -m venv env
   # Windows:
   .\env\Scripts\activate
   # Linux / macOS:
   source env/bin/activate
   ```

3. **Install PyTorch with CUDA & Diffusers dependencies:**
   ```bash
   pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
   pip install django diffusers transformers accelerate pillow requests
   ```

4. **Initialize database migrations:**
   ```bash
   python manage.py migrate
   ```

5. **Start the development server:**
   ```bash
   python manage.py runserver
   ```
   Open [http://localhost:8000](http://localhost:8000) in your web browser.

---

## 🎨 Creative Workflow

1. **Select Style**: Choose between the **Comic** or **Manga** studio in the navigation bar.
2. **Prompt & Generate**: Type your character and scene prompt. The pipeline automatically tunes the parameters for authentic comic art.
3. **Compose & Dialogue**: Drag dialogue balloons, type dialogue with authentic comic fonts, and place impact overlays.
4. **Save**: Click **Save Page** to store the rendered composition in your library.

---

## 📄 License

This project is licensed under the MIT License.
