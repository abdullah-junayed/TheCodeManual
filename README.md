# TheCodeManual 📚

**Your comprehensive guide to mastering web development, systems programming, and professional environment setup.**

TheCodeManual is an open, self-hosted documentation project built with [MkDocs](https://www.mkdocs.org/) and the [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/) theme. It covers everything from writing your first line of markup to debugging memory leaks in C — with dark/light mode, a searchable interface, and a structured learning path.

![MkDocs](https://img.shields.io/badge/MkDocs-1.6.1-2A6D46?logo=materialformkdocs&logoColor=white)
![Material](https://img.shields.io/badge/Material%20for%20MkDocs-9.7.7-526CFE)
![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green)

---

## 📖 Table of Contents

- [✨ Features](#features)
- [🗂️ Docs Structure](#docs-structure)
- [🚀 Getting Started](#getting-started)
- [🔧 Installation](#installation)
- [▶️ Running Locally](#running-locally)
- [🛠️ Building the Site](#building-the-site)
- [📁 Project Structure](#project-structure)
- [📈 Recommended Learning Path](#recommended-learning-path)
- [🤝 Contributing](#contributing)
- [🪪 License](#license)
- [👤 Author](#author)

---

## ✨ Features

- **🌗 Dark / Light Mode** — Automatic theme switching based on system preferences, with manual overrides.
- **🔍 Full-Text Search** — Search across every guide instantly from the top navigation bar.
- **📱 Responsive Design** — Looks great on desktop, tablet, and mobile.
- **🧭 Structured Learning Path** — A recommended progression from workspace setup → command line → web → C.
- **📚 Beginner to Advanced** — Guides are written step-by-step, each lesson building on the previous one.
- **⚡ Pure Markdown** — Content lives in simple `.md` files; no build tooling beyond MkDocs.

---

## 🗂️ Docs Structure

| Module | Path | Status |
| :--- | :--- | :---: |
| Home / Landing Page | `docs/index.md` | ✅ |
| VS Code Setup | `docs/vscode-setup/` | ✅ |
| Windows CMD Reference Guide | `docs/windows-cmd-reference-guide/` | ✅ |
| Linux Command Line Reference Guide | `docs/linux-command-line-reference-guide/` | ✅ |
| Nix Package Manager | `docs/nix-package-manager/` | ✅ |
| HTML5 Ultimate Guide | `docs/html-guide/` | ✅ |
| CSS3 Ultimate Guide | `docs/css-guide/` | ✅ |
| JavaScript (ES6+) Guide | `docs/javascript-guide/` | 🔜 |
| C Programming Guide | `docs/c-programming/` | 🔜 |

### 🌐 Web Development
- **HTML5** — The structural foundation of the web. Semantic markup, forms, media, and SEO basics.
- **CSS3** — The visual layer. Syntax, selectors, layout, Flexbox, Grid, animations, and responsive design.
- **JavaScript (ES6+)** — *Coming soon.* The interactive engine — DOM manipulation, async programming, and modern syntax.

### 💻 Core Programming
- **C Programming** — *Coming soon.* The mother of modern languages — pointers, manual memory management, and data structures.

### 🛠️ Workspace Setup
- **VS Code Mastery** — Essential extensions, keyboard shortcuts, themes, fonts, and debugging configurations for Web and C development.

### 💻 Command Line Fundamentals
- **Linux Command Line (Bash)** — Navigation, permissions, process management, shell scripting, pipes, and system administration.
- **Windows Command Prompt (CMD)** — File operations, networking, system configuration, batch scripting, and troubleshooting.
- **Nix Package Manager** — Declarative package installation, reproducible environments, Nix shells, channels, and flakes.

---

## 🚀 Getting Started

TheCodeManual is built with [MkDocs](https://www.mkdocs.org/), a fast and simple static site generator for project documentation written in Python. You only need Python 3.10+ and `pip`.

### 🔧 Installation

Clone the repository:

```bash
git clone https://github.com/your-username/TheCodeManual.git
cd TheCodeManual/the_code_manual
```

Create a virtual environment (recommended):

```bash
python -m venv venv
source venv/bin/activate        # Linux / macOS
venv\Scripts\activate           # Windows
```

Install the dependencies:

```bash
pip install -r requirements.txt
```

### ▶️ Running Locally

Start the live-reloading development server:

```bash
mkdocs serve
```

Then open [http://127.0.0.1:8000](http://127.0.0.1:8000) in your browser. Any change you make to a `.md` file will be reflected instantly.

### 🛠️ Building the Site

Generate the static site into the `site/` directory (ignored by git):

```bash
mkdocs build
```

To deploy to [GitHub Pages](https://pages.github.com/):

```bash
mkdocs gh-deploy
```

---

## 📁 Project Structure

```
TheCodeManual/
├── .gitignore                      # Ignored files (site/, venv/, etc.)
├── README.md
└── the_code_manual/
    ├── mkdocs.yml                  # MkDocs configuration & navigation
    ├── requirements.txt            # Pinned Python dependencies
    └── docs/                       # All documentation content (Markdown)
        ├── index.md                # Home page
        ├── html-guide/             # HTML5 guide (8 steps)
        ├── css-guide/              # CSS3 guide
        ├── javascript-guide/       # JS guide (in progress)
        ├── c-programming/          # C guide (in progress)
        ├── vscode-setup/           # VS Code configuration
        ├── linux-command-line-reference-guide/
        ├── windows-cmd-reference-guide/
        └── nix-package-manager/
```

---

## 📈 Recommended Learning Path

Follow this progression to build your skills logically:

1. **[Set up VS Code](the_code_manual/docs/vscode-setup/index.md)** — build a professional, efficient workspace.
2. **[Windows CMD Reference Guide](the_code_manual/docs/windows-cmd-reference-guide/index.md)** — learn command-line fundamentals.
3. **[Linux Command Line Reference Guide](the_code_manual/docs/linux-command-line-reference-guide/index.md)** — master powerful shell workflows.
4. **[Nix Package Manager](the_code_manual/docs/nix-package-manager/index.md)** — learn reproducible software management.
5. **[HTML](the_code_manual/docs/html-guide/index.md)** — understand structure and page markup.
6. **[CSS](the_code_manual/docs/css-guide/index.md)** — learn to style and position elements.
7. **[JavaScript](the_code_manual/docs/javascript-guide/index.md)** — add logic and interactivity. *(coming soon)*
8. **[C Programming](the_code_manual/docs/c-programming/index.md)** — build a deep understanding of memory and systems. *(coming soon)*

---

## 🤝 Contributing

Contributions are welcome! If you'd like to improve existing guides, fix typos, or add new modules:

1. Fork the repository.
2. Create a feature branch: `git checkout -b feature/your-feature`
3. Add or edit content under `the_code_manual/docs/`.
4. Commit your changes with a clear message.
5. Open a pull request.

---

## 🪪 License

This project is licensed under the **MIT License**. See the [LICENSE](LICENSE) file for details.

---

## 👤 Author

- **Md. Abdullah Junayed** — [@abdullah-junayed](https://github.com/abdullah-junayed)

> *Maintained by TheCodeManual Team. Happy Coding!*
