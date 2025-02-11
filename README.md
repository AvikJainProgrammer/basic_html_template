# basic_html_template
Contains templates to use in other projects

#Sample project file structure
```
/my-project
│─── 📄 index.html            # Main HTML file
│─── 📄 about.html            # Example additional page
│─── 📄 contact.html          # Example additional page
│
├─── 📂 assets                # Stores all resources
│    ├── 📂 css               # Stylesheets
│    │   ├── styles.css       # Main CSS file
│    │   ├── reset.css        # Optional reset/normalize file
│    │   ├── theme.css        # Optional for color themes
│    │
│    ├── 📂 js                # JavaScript files
│    │   ├── script.js        # Main JavaScript file
│    │   ├── utils.js         # Utility/helper functions
│    │
│    ├── 📂 images            # Image assets
│    │   ├── logo.png         # Logo image
│    │   ├── header.png       # Header image
│    │
│    ├── 📂 fonts             # Custom fonts
│    │   ├── inter.woff2      # Example font file
│    │   ├── inter.ttf        # Alternative format
│    │
│    ├── 📂 icons             # Icons (SVG, PNG)
│    │   ├── menu.svg         # Example icon
│    │   ├── user.svg         # Example icon
│
├─── 📂 components            # Optional: Reusable HTML components (for larger projects)
│    ├── header.html          # Header component
│    ├── footer.html          # Footer component
│
├─── 📂 data                  # Optional: JSON or other data files
│    ├── content.json         # Example JSON data file
│
├─── 📂 libs                  # Optional: External libraries (e.g., jQuery, Bootstrap)
│    ├── 📂 bootstrap         # Bootstrap CSS/JS
│    ├── 📂 jquery            # jQuery files
│
└─── 📄 README.md             # Project documentation

```

When linking to assets (CSS, JS, images, fonts, etc.) in an HTML project, **best practices** depend on the project structure and deployment environment. Here are **the best ways to link assets correctly and efficiently**:

---

## **1️⃣ CSS Files**
### ✅ **Best Practice (Relative Path)**
```html
<link rel="stylesheet" href="assets/css/styles.css">
```
- Keeps your project portable and works across environments.
- Avoids absolute paths (`C:/Users/...` or `/Users/...`).

---

## **2️⃣ JavaScript Files**
### ✅ **Best Practice (Before `</body>`)**
```html
<script src="assets/js/script.js" defer></script>
```
- **Use `defer`** to load scripts without blocking HTML rendering.
- **Avoid inline JS** in `<script>` tags inside HTML.

---

## **3️⃣ Images**
### ✅ **Best Practice (Relative Path)**
```html
<img src="assets/images/logo.png" alt="Website Logo">
```
- **Relative paths** work across different environments.
- Use **optimized formats** (WebP, PNG, SVG for scalability).

---

## **4️⃣ Fonts**
### ✅ **Best Practice (Using CSS)**
#### **Google Fonts (CDN)**
```css
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500&display=swap');
body {
    font-family: 'Inter', sans-serif;
}
```
#### **Self-hosted Fonts**
```css
@font-face {
    font-family: 'CustomFont';
    src: url('../fonts/custom-font.woff2') format('woff2');
}
body {
    font-family: 'CustomFont', sans-serif;
}
```
- **Use `woff2` format** (most optimized for the web).
- **Keep fonts inside** `assets/fonts/` for better organization.

---

## **5️⃣ Icons (SVG, FontAwesome)**
### ✅ **Best Practice (SVG for best performance)**
```html
<img src="assets/icons/menu.svg" alt="Menu Icon">
```
#### **For FontAwesome (CDN)**
```html
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
<i class="fa-solid fa-user"></i>
```
- **SVG files load faster and scale better**.
- **Avoid inline `<svg>` unless necessary**.

---

## **6️⃣ External Libraries (CDN vs Local)**
### **CDN (Fast, Always Updated)**
```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script>
```
### **Self-hosted (For Offline Use)**
```html
<script src="assets/libs/jquery/jquery.min.js"></script>
```
- **CDN is faster**, but **local files** ensure offline availability.
- **Use local libraries** if your project **must work offline**.

---

## **7️⃣ Favicon (Website Icon)**
### ✅ **Best Practice (Different Sizes)**
```html
<link rel="icon" type="image/png" sizes="32x32" href="assets/icons/favicon-32x32.png">
```
- Always include a **favicon** for branding.
- Provide **multiple sizes** (`16x16`, `32x32`, `apple-touch-icon`).

---

## **🚀 Pro Tips**
✅ **Use relative paths (`assets/...`)** instead of absolute (`C:/Users/...`).  
✅ **Organize assets properly** (`css`, `js`, `images`, `fonts`).  
✅ **Use a CDN for common libraries** (Google Fonts, FontAwesome).  
✅ **Compress images** (WebP > PNG > JPG for better performance).  
✅ **Use `defer` or `async` for scripts** to speed up page load.  

Following these best practices ensures **faster load times, better organization, and future scalability**! 🚀

TODO: CSS guide line
