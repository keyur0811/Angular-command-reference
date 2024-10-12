# Environment Builds

This document outlines the commands for building an Angular application for various environments, including development, production, and custom configurations.

## Build for Development
To build your application for development, use the following command:
```bash
ng build
```
This builds the app in development mode, using the configurations specified in `angular.json` for the default environment.

## Build for Production
To build your application for production with optimizations, run:
```bash
ng build --prod
```
This command includes optimizations such as Ahead of Time (AOT) compilation, minification, and tree shaking to reduce the bundle size and improve performance.

### Alternative Production Build Command
You can also use the following command to build for production:
```bash
ng build --configuration=production
```
This command explicitly specifies the production configuration defined in your `angular.json` file.

## Ahead of Time Compilation (AOT)
To enable AOT compilation during the build process, use:
```bash
ng build --aot
```
AOT compilation can improve performance by pre-compiling your templates.

## Enabling Source Maps
To include source maps in your production build for easier debugging, use:
```bash
ng build --source-map
```
Source maps allow you to trace errors back to your TypeScript code.

## Enabling Differential Loading (if applicable)
Angular CLI supports differential loading, which serves different bundles to modern and legacy browsers. To enable this, make sure your `browserslist` configuration supports it, then build as follows:
```bash
ng build --prod
```
This automatically generates the appropriate bundles for different browser capabilities.

## Build for a Specific Environment
If you have defined multiple environments in your `angular.json`, you can build for a specific environment using:
```bash
ng build --configuration=environment-name
```
Replace `environment-name` with the desired environment (e.g., `staging`, `qa`, etc.).

## Analyzing Bundle Size
To analyze your build's bundle size and structure, use:
```bash
ng build --stats-json
```
This generates a `stats.json` file that can be used with tools like Webpack Bundle Analyzer to inspect the size of your application bundles.

## Deploying to Firebase Hosting
If you are deploying your Angular app to Firebase, use:
```bash
ng deploy
```
Make sure you have configured your Firebase settings in your `angular.json` and that you have the AngularFire CLI installed.
```

This `Environment-Builds.md` file provides a comprehensive overview of the various commands and options for building your Angular application across different environments, making it a useful reference for your GitHub repository.