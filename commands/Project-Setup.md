# Project Setup

This section covers the commands for setting up a new Angular project and serving it locally.

### **1. Create a New Angular Project**

To create a new Angular project, run:

```bash
ng new project-name
```

This command initializes a new project in a folder named `project-name`. You will be prompted to choose:
- Whether you want to add Angular routing (yes/no).
- The stylesheet format to use (CSS, SCSS, SASS, LESS, etc.).

Options:
- Add routing: `--routing`
- Use a specific style format: `--style=scss | css | sass | less`

Example with options:
```bash
ng new my-app --routing --style=scss
```

---

### **2. Serve the Application**

To serve the application locally for development, use:

```bash
ng serve
```

The app will be available at `http://localhost:4200` by default.

Options:
- **Change port:** You can specify a different port using the `--port` option.
  
Example:
```bash
ng serve --port 8080
```

Additional options:
- **Disable auto-open in browser:** Prevent Angular from automatically opening the browser.
  ```bash
  ng serve --open=false
  ```
- **Specify host and port:**
  ```bash
  ng serve --host 0.0.0.0 --port 8080
  ```

---

### **3. Building the Application**

To build the Angular project for production or development environments, run:

```bash
ng build
```

By default, the build will be generated in the `dist/` folder.

Options:
- **Build for production:** 
  ```bash
  ng build --prod
  ```
  This command builds a production-optimized version of your application with Ahead-of-Time (AOT) compilation, minification, and tree-shaking.
  
- **Output path:** Specify a different output directory.
  ```bash
  ng build --output-path=dist/custom-folder
  ```

---

### **4. Watch for Changes**

To automatically rebuild the project whenever changes are made, use:

```bash
ng serve --watch
```

This command watches for changes and updates the local server accordingly without manually refreshing.

---

### **5. Serve with HTTPS**

To serve the app with HTTPS (using a self-signed certificate), run:

```bash
ng serve --ssl=true
```

Options:
- Use custom SSL certificates:
  ```bash
  ng serve --ssl=true --ssl-cert="/path/to/cert" --ssl-key="/path/to/key"
  ```

---

### **6. Run the App in Different Environments**

To specify a build environment (e.g., development, staging, or production), use:

```bash
ng serve --configuration=environment-name
```

Example:
```bash
ng serve --configuration=production
```

By default, Angular provides `development` and `production` configurations. You can create custom environments in the `angular.json` file.

---

This covers the basics of setting up and serving an Angular project! You can always refer back here for quick access to the essential commands.