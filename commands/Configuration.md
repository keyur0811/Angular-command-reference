# Configuration

This document outlines the Angular CLI commands related to configuring your Angular project and managing environment settings.

## Set Configuration Options

You can set or retrieve configuration values in the `angular.json` or `.angular-cli.json` file using the following command:

```bash
ng config [key] [value]
```

### Example:
Set the default project:
```bash
ng config defaults.project "my-default-project"
```

## Set Environment Variables for Build

You can specify which environment configuration to use when building your application. The common environment files are usually located in the `src/environments/` directory.

### Build for Development
```bash
ng build
```
This builds the application using the development environment settings.

### Build for Production
```bash
ng build --configuration=production
```
This builds the application using the production environment settings.

## Enable Source Maps

To include source maps in your build (useful for debugging), you can run:

```bash
ng build --source-map
```
This allows you to trace back to your original source code in the browser's developer tools.

## Custom Environment Configurations

You can create custom environment files (e.g., `environment.staging.ts`) and specify them in your `angular.json` file under the "configurations" section of the build options.

### Example:
```json
"configurations": {
  "production": {
    "fileReplacements": [
      {
        "replace": "src/environments/environment.ts",
        "with": "src/environments/environment.prod.ts"
      }
    ]
  },
  "staging": {
    "fileReplacements": [
      {
        "replace": "src/environments/environment.ts",
        "with": "src/environments/environment.staging.ts"
      }
    ]
  }
}
```

## Enable Service Worker for PWA

To configure your Angular application as a Progressive Web App (PWA), you can enable the service worker:

```bash
ng add @angular/pwa
```

This command will automatically configure the necessary settings in your project, including the `ngsw-config.json` file and the `angular.json` file.

## Angular CLI Configurations

You can view all available configurations for the Angular CLI by using:

```bash
ng config --global
```

This command lists all the configuration options you can set globally for the Angular CLI.

## Additional Notes

- Always refer to the [Angular CLI Documentation](https://angular.io/cli) for the latest updates and features regarding configuration and other commands.

### Instructions to Add
1. Create a file named `Configuration.md` in the `commands` directory of your GitHub repository.
2. Copy and paste the above content into that file.
3. Save the changes and commit to your repository.