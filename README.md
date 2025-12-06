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

---

## For Production:

<!-- Minimal setup -->
<textarea class="lazy[m]" name="content" id="editor1">Your content here</textarea>

<!-- With specific dimensions -->
<textarea class="lazy[m]" style="width: 800px; height: 400px;">Content</textarea>

<!-- Multiple editors on one page -->
<textarea class="lazy[xs]" id="title">Title (bold/italic only)</textarea>
<textarea class="lazy[xxl]" id="content">Full content editor</textarea>
<textarea class="lazy[1,2,7]" id="summary">Summary (bold, italic, links)</textarea>

---

📦 Installation
Option 1: Single File (Recommended)
Download lazyeditor.html

Copy the <style> and <script> sections into your project

That's it!

Option 2: CDN (Coming Soon)

<!-- Future release -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/HangKebun74/lazyeditor@main/lazyeditor.css">
<script src="https://cdn.jsdelivr.net/gh/HangKebun74/lazyeditor@main/lazyeditor.js"></script>

Option 3: Local Files

<!-- Save these files locally -->
<link rel="stylesheet" href="lazyeditor.css">
<script src="lazyeditor.js"></script>

Option 4: NPM/Yarn (Future)

# Planned for v2.0
npm install lazyeditor
# or
yarn add lazyeditor

---

🎮 Usage Examples
Basic Example

<!-- Basic editor with default buttons -->
<textarea class="lazy[m]" id="basic-editor">
    <h2>Welcome to LazyEditor</h2>
    <p>This is a <strong>rich text editor</strong> with <em>simple buttons</em>.</p>
    <ul>
        <li>Easy to use</li>
        <li>No dependencies</li>
        <li>Lightweight</li>
    </ul>
</textarea>

Form Integration

<form action="/submit" method="post">
    <label for="title">Title:</label>
    <textarea class="lazy[xs]" name="title" id="title" required>Enter title</textarea>
    
    <label for="content">Content:</label>
    <textarea class="lazy[xxl]" name="content" id="content" rows="10" required>
        Enter your content here...
    </textarea>
    
    <button type="submit">Submit</button>
</form>

Dynamic Loading

// Load editor on dynamic content
function addEditor() {
    const container = document.getElementById('editor-container');
    container.innerHTML = '<textarea class="lazy[m]" id="dynamic-editor">New content</textarea>';
    
    // Reinitialize if needed
    if (window.LazyEditor && window.LazyEditor.refresh) {
        window.LazyEditor.refresh();
    }
}

Getting Content

// Get HTML content
const htmlContent = document.querySelector('textarea.lazy[m]').value;

// Get plain text (strip HTML)
const plainText = document.querySelector('.le-design').innerText;

// Listen for changes
document.querySelector('textarea.lazy[m]').addEventListener('change', function(e) {
    console.log('Content changed:', e.target.value);
    saveToDatabase(e.target.value);
});

Setting Content Programmatically

// Set content via textarea
document.querySelector('textarea.lazy[m]').value = '<p>New content</p>';

// Refresh editor to show new content
if (window.LazyEditor && window.LazyEditor.refresh) {
    window.LazyEditor.refresh();
}

---

🔧 Preset System
LazyEditor comes with 7 built-in presets and custom button selection:

Built-in Presets
Preset	Buttons	Description	Best For
lazy[zzz]	None	Empty toolbar	Simple text with view toggle only
lazy[xs]	B, I	Minimal formatting	Titles, short text
lazy[s]	B, I, *	Basic text + lists	Simple content
lazy[m]	B, I, *, 1., URL	Standard formatting	Default - Most use cases
lazy[l]	B, I, U, *, 1., URL, ---	Enhanced formatting	Articles, blogs
lazy[xl]	B, I, U, S, *, 1., URL, ---	Full text formatting	Detailed content
lazy[xxl]	B, I, U, S, *, 1., URL, ---, CODE, QUOTE, X, PRN, RTL	Complete feature set	Advanced users, developers

---

Custom Button Selection
Pick specific buttons by their ID numbers (1-15):

<!-- Only Bold(1), Italic(2), Link(7) -->
<textarea class="lazy[1,2,7]">Custom buttons</textarea>

<!-- Your selection: 1,5,6,7,8 (Bold, Lists, Link, Line) -->
<textarea class="lazy[1,5,6,7,8]">Article editor</textarea>

<!-- Just code and quote buttons -->
<textarea class="lazy[10,11]">Code snippets only</textarea>

---

🎯 Button Reference


ID	Button	Command	Description	Shortcut
1	B	bold	Toggle bold text	Ctrl+B
2	I	italic	Toggle italic text	Ctrl+I
3	U	underline	Toggle underline text	Ctrl+U
4	S	strikethrough	Strikethrough text	-
5	*	insertUnorderedList	Bullet (unordered) list	-
6	1.	insertOrderedList	Numbered (ordered) list	-
7	URL	createLink	Insert hyperlink	Ctrl+K
8	---	insertHorizontalRule	Horizontal line	-
9	IMG	insertImage	Insert image (placeholder)	-
10	CODE	formatCode	Code block (<pre><code>)	-
11	QUOTE	formatQuote	Blockquote (<blockquote>)	-
12	TABLE	insertTable	Insert table (placeholder)	-
13	X	removeFormat	Remove formatting from selection	-
14	PRN	print	Print editor content	-
15	RTL	toggleRTL	Toggle RTL/LTR direction	-

---

Button Usage Notes:
Bold/Italic/Underline: Toggle on selected text

Lists: Creates list at cursor or converts selected text

Link: Prompts for URL, requires http:// or https://

Code Block: Wraps selection in <pre><code>

Quote: Wraps selection in <blockquote>

Remove Format: Clears all formatting from selected text

RTL: Changes text direction of selected element

---

⚙️ Configuration
Edit settings in the <script> section of LazyEditor:

const LE_CONFIG = {
    // ==================== BEHAVIOR ====================
    debugMode: true,                    // true = show debug panel, false = hide for production
    defaultHeight: '160px',             // Initial editor height (CSS value)
    hideFormatButtonsInHtmlMode: true,  // Hide format buttons in HTML view
    enablePlaceholder: true,            // Show "Type here..." when empty
    debounceDelay: 250,                 // Auto-save delay (milliseconds)
    defaultPreset: 'm',                 // Default preset when no config specified
    
    // ==================== DISPLAY ====================
    showBranding: true,                 // Show "LazyEditor" in status bar
    brandingText: 'LazyEditor',         // Custom branding text
    showVersion: true,                  // Show version number
    versionText: 'v1.0.0',              // Version text
    showPresetInfo: true,               // Show preset name in status bar
    
    // ==================== BUTTONS ====================
    buttons: {
        1:  { text: 'B', cmd: 'bold', title: 'Bold (Ctrl+B)', desc: 'Bold text' },
        2:  { text: 'I', cmd: 'italic', title: 'Italic (Ctrl+I)', desc: 'Italic text' },
        // ... all 15 buttons defined here
    },
    
    // ==================== PRESETS ====================
    presets: {
        'zzz': [],                      // No buttons
        'xs':  [1, 2],                  // Bold, Italic
        's':   [1, 2, 5],               // + Bullet List
        'm':   [1, 2, 5, 6, 7],         // + Numbered List, Link [DEFAULT]
        'l':   [1, 2, 3, 5, 6, 7, 8],   // + Underline, Horizontal Line
        'xl':  [1, 2, 3, 4, 5, 6, 7, 8],// + Strikethrough
        'xxl': [1, 2, 3, 4, 5, 6, 7, 8, 10, 11, 13, 14, 15] // Full featured
    }
};

Configuration Tips:
Production: Set debugMode: false

Custom Height: Use CSS values: '300px', '50vh', 'auto'

Custom Presets: Add your own to the presets object

Button Text: Change button labels in the buttons configuration

---

⌨️ Keyboard Shortcuts
Shortcut	Action	Works In
Ctrl + B	Toggle bold	Design mode only
Ctrl + I	Toggle italic	Design mode only
Ctrl + U	Toggle underline	Design mode only
Ctrl + K	Insert link	Design mode only
Tab	Indent (in lists)	Design mode only
Shift + Tab	Outdent (in lists)	Design mode only
Ctrl + Z	Undo (browser default)	Both modes
Ctrl + Y	Redo (browser default)	Both modes
Ctrl + A	Select all	Both modes

---

Browser Compatibility:
Works in Chrome, Firefox, Edge, Safari

Mac: Use Cmd instead of Ctrl

Some shortcuts may be overridden by browser extensions

---

📝 API & Methods
LazyEditor exposes a global LazyEditor object with these methods:

Public Methods

// Refresh all editors (after dynamic content changes)
LazyEditor.refresh();

// Get debug information
const debugInfo = LazyEditor.getDebugInfo();
console.log(debugInfo.summary); // "No errors detected" or error summary
console.log(debugInfo.errors);  // Number of errors
console.log(debugInfo.lastError); // Last error object

// Manual initialization (if auto-init fails)
LazyEditor.init();

Events
The original textarea fires standard DOM events:

const editorTextarea = document.querySelector('textarea.lazy[m]');

// Content changed
editorTextarea.addEventListener('change', function(e) {
    console.log('Content saved:', e.target.value);
});

// Input events (real-time)
editorTextarea.addEventListener('input', function(e) {
    console.log('User is typing...');
});

// Form submission
document.querySelector('form').addEventListener('submit', function(e) {
    const content = editorTextarea.value;
    // Submit content normally
});

Content Methods

// Get HTML
const html = document.querySelector('textarea.lazy[m]').value;

// Get plain text
const plainText = document.querySelector('.le-design').innerText;

// Check if empty
const isEmpty = document.querySelector('.le-design').innerHTML.trim() === '';

// Count characters (HTML stripped)
const charCount = document.querySelector('.le-design').innerText.length;

🐛 Debug Mode
When debugMode: true, a yellow debug panel appears with:

Debug Symbols
Symbol	Color	Meaning
>	Blue	Information message
+	Green	Success/operation completed
!	Orange	Warning/non-critical issue
x	Red	ERROR - needs attention
Error Examples in Debug Panel

> LAZYEDITOR v1.0.0 INITIALIZED
> System: Ready
> Mode: Debug (set debugMode: false for production)
----------------------------------------
x Invalid URL entered: example.com
  Context: URL missing protocol (http:// or https://)
  Fix: Always include http:// or https:// at the beginning of URLs
  Code location: Stack trace line 42

Common Debug Scenarios
Invalid configuration: Shows preset parsing errors

Button click errors: Shows why a command failed

View switching issues: Debugs HTML/Design mode problems

Content sync problems: Shows sync failures

Turning Off Debug
For production, set debugMode: false in LE_CONFIG.

---

❓ FAQ
Q: Why ASCII-only buttons?
A: ASCII buttons ensure:

No icon fonts or images needed

Universal compatibility

Smaller file size

Easier customization

Consistent appearance across all systems

Q: How do I save content to a database?
A: The original textarea contains the HTML. Submit it normally:

// PHP example
$content = $_POST['content'];
$stmt = $pdo->prepare("INSERT INTO articles (content) VALUES (?)");
$stmt->execute([$content]);

Q: Can I use it with React/Vue/Angular?
A: Yes! LazyEditor works with any framework:

// React example
function MyComponent() {
    useEffect(() => {
        // Initialize after component mounts
        if (window.LazyEditor) {
            window.LazyEditor.refresh();
        }
    }, []);
    
    return <textarea className="lazy[m]" defaultValue="Content" />;
}

Q: How to customize the look?
A: Edit CSS variables in the :root section:

:root {
    --le-bg: #ffffff;           /* Editor background */
    --le-border: #d1d5db;       /* Border color */
    --le-btn-bg: #f3f4f6;       /* Button background */
    --le-btn-color: #374151;    /* Button text color */
    /* ... more variables */
}

Q: Why are IMG and TABLE buttons not working?
A: These are placeholders for v2.0. Currently, you can:

Use HTML mode to manually add <img> or <table> tags

Wait for v2.0 which will implement these features

Submit a PR to add these features

Q: How to handle XSS security?
A: Always sanitize HTML on the server:

// PHP with HTML Purifier
$config = HTMLPurifier_Config::createDefault();
$purifier = new HTMLPurifier($config);
$clean_html = $purifier->purify($content);

Q: Can I add custom buttons?
A: Currently via configuration only. In v2.0:

// Planned API
LazyEditor.addButton('custom', {
    text: 'CUSTOM',
    action: function() {
        // Custom logic
    }
});

Q: Mobile touch support?
A: Yes! Fully touch-enabled:

Buttons work with touch

Soft keyboard works normally

No hover states that break mobile

---

🔄 Changelog
v1.0.0 (Current) - December 2025
✅ Initial release

✅ 15 formatting buttons

✅ 7 built-in presets

✅ Custom button selection

✅ Design & HTML view modes

✅ Debug mode with error highlighting

✅ Keyboard shortcuts

✅ RTL support

✅ Print functionality

✅ Auto-sync between views

✅ Status bar with branding

✅ MIT License

v1.1.0 (Planned)
Image upload support

Table insertion

Custom button API

Undo/Redo stack

Localization support

Dark mode

Plugin system

v2.0.0 (Future)
NPM package

TypeScript definitions

Framework wrappers (React, Vue, Angular)

Advanced image handling

Table editing

Advanced list styles

Math equation support

---

🤝 Contributing
We love contributions! Here's how:

Ways to Contribute
Report bugs - Create an issue

Suggest features - Use GitHub Issues

Submit code - Fork and create a Pull Request

Improve documentation - Edit README.md

Share - Star the repo, tell others!

Development Setup
# 1. Fork the repository
# 2. Clone your fork
git clone https://github.com/your-username/lazyeditor.git
cd lazyeditor

# 3. Create a branch
git checkout -b feature/your-feature-name

# 4. Make changes
# 5. Test thoroughly

# 6. Commit
git add .
git commit -m "Add: Your feature description"

# 7. Push
git push origin feature/your-feature-name

# 8. Create Pull Request

Coding Standards
Use consistent indentation (4 spaces)

Comment complex logic

Update documentation when changing APIs

Test in multiple browsers

Keep it dependency-free

Areas Needing Help
Image upload implementation

Table editing features

Accessibility improvements

Performance optimization

Unit tests

Documentation translations

🐛 Known Issues
Current Limitations
IMG button - Placeholder only (use HTML mode)

TABLE button - Placeholder only (use HTML mode)

Keyboard shortcuts - May conflict with browser extensions

Internet Explorer - Not supported (use Edge)

Very old browsers - May have limited functionality

Workarounds
Issue	Workaround
Need images	Manually add <img src="..." alt="..."> in HTML mode
Need tables	Write HTML table code in HTML mode
Print not working	Check popup blockers
RTL not working	Select text first, then click RTL
Browser-Specific Issues
Safari: Some execCommand variations

Firefox: Different CSS handling in contenteditable

Mobile browsers: Soft keyboard may hide toolbar

---

📄 License
MIT License
Copyright © 2024 HangKebun74

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

Summary of Rights:
✅ Use commercially

✅ Modify and distribute

✅ Use privately

✅ Place warranty

✅ Sublicense

✅ Hold liable

❌ Must include copyright notice

❌ Must include license text

---

🙏 Acknowledgments
Credits
Creator: HangKebun74

Inspiration: Early WYSIWYG editors, minimal design principles

Testers: Early adopters and GitHub contributors

Community: All who report issues and suggest improvements

Similar Projects
TinyMCE - Feature-rich editor

Quill - Modern rich text editor

MediumEditor - Medium-like editor

CKEditor - Enterprise editor

Special Thanks To:
The vanilla JavaScript community

GitHub for hosting

All open-source projects that inspired this work

Users who choose simplicity over complexity

---

📞 Contact & Support
Getting Help
GitHub Issues: Report bugs/request features

Email: Add your email here if desired

Twitter: Add your handle if desired

Support This Project
⭐ Star the repository on GitHub

🍴 Fork it and create derivatives

📢 Share with your network

🐛 Report issues you encounter

💡 Suggest improvements

Star History

2024-12: ★ Initial release

---

2024-12: ★ Initial release

---

HTML Version (If You Want)
If you want an HTML version of the README that looks beautiful on GitHub Pages, here's a separate documentation.html file you could create:

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>LazyEditor Documentation</title>
    <style>
        /* Add your styling here */
    </style>
</head>
<body>
    <!-- HTML version of the documentation -->
</body>
</html>



