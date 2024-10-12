# Production Build

Building your Angular application for production optimizes the code for performance and reduces the file size, making it ready for deployment. Here are the essential commands and options for production builds.

## 1. Build for Production
To build your application for production, run the following command:
```bash
ng build --prod
```
### Options:
- **--prod**: This flag enables optimizations such as Ahead-of-Time (AOT) compilation, minification, and tree shaking to reduce the bundle size and improve load times.

## 2. Build with AOT (Ahead-of-Time) Compilation
You can explicitly enable AOT compilation (though it is enabled by default with `--prod`) using:
```bash
ng build --aot
```
### Benefits of AOT:
- Faster rendering because the browser downloads a precompiled version of the application.
- Fewer asynchronous requests since templates are compiled during the build process.

## 3. Enable Source Maps for Debugging
If you want to include source maps in your production build for easier debugging, use:
```bash
ng build --prod --source-map
```
### Note:
- Be cautious with source maps in production, as they can expose your source code. Use them only in trusted environments.

## 4. Enabling Hot Module Replacement (HMR)
During development, you can enable Hot Module Replacement to instantly update your application without a full reload:
```bash
ng serve --hmr
```
### Note:
- HMR is not recommended for production but is useful during development to improve efficiency.

## 5. Analyzing Bundle Size
To analyze your application's bundle size and identify large modules, run:
```bash
ng build --prod --stats-json
```
This generates a `stats.json` file, which you can analyze using tools like Webpack Bundle Analyzer to identify and reduce large dependencies.

## 6. Deploying to Firebase
If you're deploying your application to Firebase Hosting, ensure you have the Firebase CLI installed, and then run:
```bash
ng deploy
```
### Steps to Set Up Firebase Hosting:
1. Install Firebase CLI globally:
   ```bash
   npm install -g firebase-tools
   ```
2. Initialize Firebase in your project:
   ```bash
   firebase init
   ```
3. Follow the prompts to set up hosting and specify your build output directory (usually `dist/project-name`).

## 7. Additional Build Options
- **Output Path**: Specify the output directory for the build:
  ```bash
  ng build --prod --output-path=custom-directory
  ```
- **Configuration**: You can build using specific configurations defined in your `angular.json`:
  ```bash
  ng build --configuration=production
  ```

## Conclusion
Building your Angular application for production is crucial for performance and user experience. Utilizing these commands and options will help ensure your app is optimized and ready for deployment.