# LazyEditor v1.0.0

<div align="center">

![LazyEditor Banner](https://via.placeholder.com/800x200/2b6cb0/ffffff?text=LAZYEDITOR+v1.0.0)
*Lightweight WYSIWYG HTML Editor - No Dependencies, ASCII Interface*

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
![GitHub file size](https://img.shields.io/github/size/HangKebun74/lazyeditor/index.html)
![No Dependencies](https://img.shields.io/badge/dependencies-none-success)
![GitHub stars](https://img.shields.io/github/stars/HangKebun74/lazyeditor?style=social)
![GitHub forks](https://img.shields.io/github/forks/HangKebun74/lazyeditor?style=social)

**🌐 Live Demo:** [https://hangkebun74.github.io/lazyeditor/](https://hangkebun74.github.io/lazyeditor/)

</div>

## 📖 Table of Contents
- [✨ Features](#-features)
- [🚀 Quick Start (10 Seconds)](#-quick-start-10-seconds)
- [📦 Installation](#-installation)
- [🎮 Usage Examples](#-usage-examples)
- [🔧 Preset System](#-preset-system)
- [🎯 Button Reference](#-button-reference)
- [⚙️ Configuration](#️-configuration)
- [⌨️ Keyboard Shortcuts](#️-keyboard-shortcuts)
- [📝 API & Methods](#-api--methods)
- [🐛 Debug Mode](#-debug-mode)
- [❓ FAQ](#-faq)
- [🔄 Changelog](#-changelog)
- [🤝 Contributing](#-contributing)
- [🐛 Known Issues](#-known-issues)
- [📄 License](#-license)
- [🙏 Acknowledgments](#-acknowledgments)

---

## ✨ Features

### 🎯 **Core Features**
- **🚫 Zero Dependencies** - Pure vanilla JavaScript, no jQuery, no frameworks
- **📦 Lightweight** - Single HTML file (45KB), no external resources
- **🔤 ASCII Interface** - Clean, text-only buttons (B, I, U, S, etc.)
- **👁️ Dual View Mode** - Toggle between Design (WYSIWYG) and HTML source
- **🔄 Auto-sync** - Real-time synchronization between all views
- **📱 Responsive** - Works perfectly on mobile, tablet, and desktop
- **⌨️ Keyboard Shortcuts** - Ctrl+B, Ctrl+I, Ctrl+U, Ctrl+K

### 🛠️ **Advanced Features**
- **🎛️ Preset System** - 7 built-in configurations or custom button selection
- **🐛 Debug Mode** - Comprehensive error reporting with helpful suggestions
- **🔀 RTL Support** - Right-to-left text direction toggle
- **🖨️ Print Functionality** - Clean print-ready formatting
- `</>` **Code Blocks** - Proper `<pre><code>` formatting
- `❝` **Quote Blocks** - Beautiful blockquote styling
- **🎨 Customizable** - Extensive configuration options via JavaScript

### 🔒 **Quality & Security**
- **📄 MIT Licensed** - Free for commercial and personal use
- **♿ Accessible** - Semantic HTML and keyboard navigation
- **🔒 No Tracking** - No analytics, no external calls, no telemetry
- **📴 Offline Ready** - Works completely offline
- **🛡️ Content Security** - No script injection vulnerabilities

---

## 🚀 Quick Start (10 Seconds)

### **For Immediate Use:**
1. **Copy** the entire content of `lazyeditor.html`
2. **Paste** it into your HTML page's `<head>` section
3. **Add** this class to any textarea: `class="lazy[m]"`

**Example:**
```html
<!DOCTYPE html>
<html>
<head>
    <!-- PASTE LAZYEDITOR CODE HERE -->
</head>
<body>
    <h1>My Page</h1>
    <textarea class="lazy[m]">Start editing here...</textarea>
</body>
</html>
