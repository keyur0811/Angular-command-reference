# Standalone Component in Angular

## Overview

Standalone components were introduced in Angular 14 to simplify the component model by allowing components to be used without needing to declare them in an NgModule. This is particularly useful for smaller applications or when you want to keep your codebase clean and maintainable.

## Creating a Standalone Component

To create a standalone component, you can use the Angular CLI with the `--standalone` option. This allows you to generate a component that does not need to be part of a module.

### Command
```bash
ng generate component component-name --standalone
```

### Example

Let's create a standalone component called `example`.

```bash
ng generate component example --standalone
```

This command generates the following files:

```
src/
└── app/
    └── example/
        ├── example.component.ts
        ├── example.component.html
        ├── example.component.css
        └── example.component.spec.ts
```

## Example Component Code

### example.component.ts
Here is an example implementation of the standalone component:

```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-example',
  standalone: true,
  templateUrl: './example.component.html',
  styleUrls: ['./example.component.css']
})
export class ExampleComponent {
  message: string = 'Hello, this is a standalone component!';
}
```

### example.component.html
Here’s how you can use the standalone component in its template:

```html
<div>
  <h1>{{ message }}</h1>
</div>
```

## Using the Standalone Component

Since `ExampleComponent` is standalone, you can use it directly in any other component or the application root without needing to declare it in a module.

### Using in App Component

To use the standalone component in the main application component, follow these steps:

1. Open the `app.component.ts` file.

2. Import the `ExampleComponent`:

   ```typescript
   import { Component } from '@angular/core';
   import { ExampleComponent } from './example/example.component';

   @Component({
     selector: 'app-root',
     standalone: true,
     template: `
       <h1>Welcome to Standalone Components Example!</h1>
       <app-example></app-example>
     `,
     imports: [ExampleComponent]  // Import the standalone component here
   })
   export class AppComponent {}
   ```

3. Now, run your application:

```bash
ng serve
```

Navigate to `http://localhost:4200` in your browser, and you should see the message from the `ExampleComponent` displayed.

## Conclusion

Standalone components are a powerful feature in Angular that allows for more flexibility and cleaner code management. You can easily create and use components without the boilerplate code required for NgModules.

Feel free to explore and implement standalone components in your projects to take advantage of this new feature!

---

### Summary of the File Content:
- **Overview:** Explains what standalone components are and their purpose.
- **Creating a Standalone Component:** Provides the command to generate a standalone component with an example.
- **Example Component Code:** Shows the TypeScript and HTML code for the standalone component.
- **Using the Standalone Component:** Instructions on how to use the standalone component in the main application component.
- **Conclusion:** Summarizes the benefits of using standalone components.

This structure should give users a clear and concise understanding of how to create and use standalone components in Angular.