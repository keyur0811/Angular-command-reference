## Advanced Features

This section covers advanced Angular features that go beyond the basics, such as standalone components, lazy loading, and newer concepts like Angular Signals.

### 1. **Standalone Components (Angular 14+)**
Standalone components allow you to create Angular components without the need to include them in NgModules, simplifying small projects and enhancing code reuse.

#### Command:
```bash
ng generate component component-name --standalone
```

#### Example:
```bash
ng generate component my-standalone-component --standalone
```

#### Usage:
You can directly use this component in other parts of the application without declaring it in a module. Make sure to import the component directly in the place where you need it:
```typescript
import { MyStandaloneComponent } from './my-standalone-component.component';
```

---

### 2. **Lazy Loading Modules**
Lazy loading allows you to load specific modules only when needed, improving application load time by reducing the initial bundle size.

#### Steps to Set Up Lazy Loading:

1. Generate a new module with routing:
    ```bash
    ng generate module feature --routing
    ```

2. Add the route in `app-routing.module.ts` using the `loadChildren` method:
    ```typescript
    const routes: Routes = [
      { path: 'feature', loadChildren: () => import('./feature/feature.module').then(m => m.FeatureModule) }
    ];
    ```

3. Configure the lazy-loaded module’s routing:
    In `feature-routing.module.ts`:
    ```typescript
    const routes: Routes = [
      { path: '', component: FeatureComponent }
    ];
    ```

This will load the `FeatureModule` only when the user navigates to the `/feature` route.

---

### 3. **Angular Signals (Experimental - Angular 16+)**
Angular Signals provide a new reactive data tracking system for change detection, offering an alternative to observables. This is still an experimental feature and not yet stable.

#### Example:
1. **Creating a Signal:**
    ```typescript
    import { signal } from '@angular/core';
    
    const counter = signal(0);
    ```

2. **Updating the Signal:**
    ```typescript
    counter.update(value => value + 1);
    ```

3. **Using Signal in Template:**
    ```html
    <div>{{ counter() }}</div>
    <button (click)="counter.update(c => c + 1)">Increment</button>
    ```

This simplifies the change detection process by tracking reactive changes in a declarative way.

---

### 4. **Strict Mode in Angular**
Strict mode provides better type checking and stricter build-time checks, ensuring higher quality code.

#### Enabling Strict Mode:
```bash
ng new project-name --strict
```

Strict mode enables:
- Strict template type checking
- Strictly typed forms
- Enhanced compiler checks

You can also enable strict mode in an existing project by updating the `angular.json`:
```json
{
  "angularCompilerOptions": {
    "strictTemplates": true
  }
}
```

---

### 5. **Zone-Less Angular (Angular 15+)**
Angular traditionally uses Zones for change detection, but newer versions support zone-less operation using the `ngZone` configuration, which can improve performance in large applications.

#### Disabling Zones:
1. Remove `Zone.js` dependency from `polyfills.ts`.
2. In `main.ts`, set `ngZone: 'noop'`:
    ```typescript
    platformBrowserDynamic().bootstrapModule(AppModule, { ngZone: 'noop' })
      .catch(err => console.error(err));
    ```

3. Use `signals` or `RxJS` to handle manual change detection.

---

### 6. **Standalone APIs**
Angular now supports more standalone APIs, like `HttpClient`, `Router`, and more, which can be imported directly without modules.

#### Example (HttpClient as Standalone):
```typescript
import { HttpClient } from '@angular/common/http';
import { bootstrapApplication } from '@angular/platform-browser';

bootstrapApplication(AppComponent, {
  providers: [HttpClient]
});
```

This simplifies the configuration process, especially for small or micro applications.

---

### 7. **Hydration for Server-Side Rendering (Angular 16+)**
Angular now supports hydration out of the box, which improves server-side rendering (SSR) by reusing the existing server-rendered HTML instead of regenerating it from scratch.

#### Setup Hydration:
1. Ensure SSR setup:
    ```bash
    ng add @nguniversal/express-engine
    ```

2. Add hydration option:
    ```typescript
    import { provideHydration } from '@angular/platform-browser';
    
    bootstrapApplication(AppComponent, {
      providers: [provideHydration()]
    });
    ```

Hydration enhances the speed of client-side bootstrapping after the server has rendered the initial page.

---

### 8. **Optimized Image Loading (Angular 15+)**
Angular introduced a built-in image directive to optimize image loading for faster rendering and smaller bundles.

#### Usage:
```html
<img ngSrc="assets/image.png" width="600" height="400" />
```

The `ngSrc` directive optimizes image loading with lazy loading and responsive images support.

---

### 9. **Signals with Directives (Angular 16+)**
Directives can now be reactive with Angular signals, providing a fine-grained and efficient way to manage change detection at the directive level.

#### Example:
```typescript
import { signal } from '@angular/core';

@Directive({
  selector: '[appMyDirective]'
})
export class MyDirective {
  private visibility = signal(false);

  toggle() {
    this.visibility.update(value => !value);
  }
}
```