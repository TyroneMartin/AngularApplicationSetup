# Setting Up Angular

## 🔄 Updating npm

To update npm, run:

```bash
[sudo] npm install -g npm
```

> 💡 Use `sudo` only if you're on macOS or Linux.

---

## 🔧 Updating the Angular CLI

First, uninstall the existing CLI versions:

```bash
[sudo] npm uninstall -g angular-cli @angular/cli
```

Then clear the npm cache:

```bash
npm cache clean --force
```

Now reinstall the latest Angular CLI:

```bash
[sudo] npm install -g @angular/cli
```

---

## 🪟 For Windows Users

If you're seeing an error like:

```
npm.ps1 cannot be loaded because running scripts is disabled on this system.
```

It’s due to PowerShell's script execution policy.

### 🔓 Temporarily Bypass the Restriction

1. **Run PowerShell as Administrator**
2. Enter the following command to allow scripts temporarily:

```powershell
Set-ExecutionPolicy -ExecutionPolicy Bypass -Scope Process
```

3. Then retry your Angular CLI command, for example:

```powershell
npm install -g @angular/cli
```

---

### 🔐 You Can Also Make It Permanent (Optional)

If you'd like to permanently allow locally-created scripts to run:

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

> This allows locally-created scripts to run while still blocking unsigned ones from the internet.

---

## 🚀 Creating a New Angular Project

To create a new Angular app, use the following format:

```bash
ng new <project-name> --no-strict --standalone=false --routing=false
```

### Example:

```bash
ng new AngularApplicationSetup --no-strict --standalone=false --routing=false
```

Then navigate into your project folder:

```bash
cd AngularApplicationSetup
```

Start the development server:

```bash
ng serve
```

Visit your app in the browser at:

```
-> Local: http://localhost:4200/
```

# Next Steps: Add Bootstrap to Angular

### 📦 Install Bootstrap 3 in Angular

## ✅ Install Bootstrap v3 via npm

Run the following command in your Angular project directory:

```bash
npm install bootstrap@3
```

After installation, Bootstrap will be located in:

```
node_modules/bootstrap
```

---

## 🛠 Add Bootstrap to `angular.json`

To include Bootstrap styles and scripts in your Angular project, open `angular.json` and update the build options:

### 🔧 Under `"styles"`:

```json
"styles": [
  "node_modules/bootstrap/dist/css/bootstrap.min.css",
  "src/styles.css"
],
```

### 🔧 Under `"scripts"`:

```json
"scripts": [
  "node_modules/bootstrap/dist/js/bootstrap.min.js"
]
```

> ⚠️ **Make sure to restart your dev server** (`ng serve`) if it's already running after updating `angular.json`.

---

## 🧩 Optional: Install jQuery (Required for Bootstrap 3 JavaScript Features)

Bootstrap 3’s JavaScript components (like modals, dropdowns, and tooltips) depend on jQuery.

To install it:

```bash
npm install jquery
```

Then include jQuery in the `"scripts"` section of your `angular.json`, before Bootstrap:

```json
"scripts": [
  "node_modules/jquery/dist/jquery.min.js",
  "node_modules/bootstrap/dist/js/bootstrap.min.js"
]
```

Useful link: https://getbootstrap.com/docs/3.4/getting-started/