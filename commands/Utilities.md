# Utilities

### **Help Command**
To get help and see a list of all available Angular CLI commands and options:
```bash
ng help
```

This command lists all possible Angular commands and their descriptions, along with available options for each.

---

### **Angular CLI Version**
To check the version of Angular and its dependencies being used in your project:
```bash
ng version
```

This will display:
- Angular CLI version
- Node.js version
- OS platform
- Angular framework versions (core, compiler, etc.)

---

### **Analyze Bundle Size**
To analyze the bundle size and get insights into which modules and libraries are taking up the most space in your build:
```bash
ng build --stats-json
```

This generates a `stats.json` file in the output directory (`dist/`) that can be used with tools like **Webpack Bundle Analyzer** to visually inspect the bundle size.

---

### **Show Project Configuration**
To view or edit the configuration options in your `angular.json` file:
```bash
ng config
```

This command shows or sets configuration values, such as:
- Build targets
- Project paths
- File replacements for different environments

---

### **Cache Management**
To clear the Angular build cache, which can help resolve build issues or free up disk space:
```bash
ng cache clean
```

---

### **Run with Debugging**
To run Angular in debug mode with more verbose logging output, helping you understand where potential issues are occurring:
```bash
ng serve --verbose
```

This provides additional debug information during the build and serve process.

---

### **Extract i18n Messages**
To extract internationalization (i18n) messages from your Angular templates for translation:
```bash
ng xi18n
```

This will generate a `.xlf` or `.json` file containing all translatable strings from your project.

---

### **Run with Custom Host and Port**
To change the default host (`localhost`) and port (`4200`) when running the Angular app locally:
```bash
ng serve --host 0.0.0.0 --port 8080
```

You can change the host to `0.0.0.0` to allow the app to be accessed on the network, and change the port to any available number.

---

### **Install a Package with ng-add**
To add new Angular packages (like Angular Material) and automatically configure them:
```bash
ng add @angular/material
```

This command installs the package and sets up any required configurations for you.