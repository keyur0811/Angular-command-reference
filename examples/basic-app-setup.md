### **basic-file-setup.md**

# Basic Angular File Setup

This guide outlines the steps to set up a basic Angular application.

## Prerequisites

Before starting, ensure you have the following installed:

1. **Node.js**: Download and install Node.js from [nodejs.org](https://nodejs.org/).
   - Confirm installation by running:
     ```bash
     node -v
     npm -v
     ```

2. **Angular CLI**: Install the Angular Command Line Interface globally.
   ```bash
   npm install -g @angular/cli
   ```

   Confirm installation by checking the version:
   ```bash
   ng version
   ```

## Step 1: Create a New Angular Project

1. Open your terminal and run the following command to create a new Angular project:
   ```bash
   ng new my-angular-app
   ```

2. When prompted, choose whether to add Angular routing (yes/no) and select the stylesheet format (CSS, SCSS, etc.).

## Step 2: Navigate to Your Project Directory

Change to the project directory:
```bash
cd my-angular-app
```

## Step 3: Serve the Application

1. Start the development server:
   ```bash
   ng serve
   ```

2. Open your web browser and navigate to `http://localhost:4200` to view your application.

## Step 4: Explore the Project Structure

Here’s a brief overview of the generated files and directories:

- **src/**: Contains the main application source code.
  - **app/**: Contains application modules and components.
  - **assets/**: Stores static assets like images and styles.
  - **environments/**: Configuration files for different environments (development, production).
- **angular.json**: Configuration file for Angular CLI.
- **package.json**: Contains project dependencies and scripts.
- **tsconfig.json**: TypeScript configuration file.

## Step 5: Generating a New Component

You can generate new components using the Angular CLI. For example, to create a new component called `my-component`, run:
```bash
ng generate component my-component
```

OR use the shorthand:
```bash
ng g c my-component
```

## Step 6: Building the Application for Production

When you’re ready to deploy your application, build it for production:
```bash
ng build --prod
```

This command compiles the application into the `dist/` directory, optimizing it for deployment.

## Conclusion

You have successfully set up a basic Angular application! Explore Angular's features further by creating components, services, and routing to build a complete application.

For more details, refer to the [official Angular documentation](https://angular.io/docs).

This file provides a clear and concise guide for setting up a basic Angular application, making it easy for users to follow along. You can add or modify sections as needed!