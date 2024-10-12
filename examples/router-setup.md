# Router Setup in Angular

This guide provides a step-by-step approach to setting up routing in an Angular application.

## 1. Setting Up Angular Routing

When creating a new Angular project, you can include Angular routing by answering `Yes` to the prompt:

```bash
ng new project-name --routing
```

If you already have a project, you can manually add routing by creating a routing module.

### Creating a Routing Module

1. **Generate a Routing Module**

   Run the following command to create a routing module:

   ```bash
   ng generate module app-routing --flat --module=app
   ```

   This command generates a routing module and imports it into the main `AppModule`.

## 2. Defining Routes

Open `app-routing.module.ts` and define your routes inside the `Routes` array.

### Example Routes

```typescript
import { NgModule } from '@angular/core';
import { RouterModule, Routes } from '@angular/router';
import { HomeComponent } from './home/home.component';
import { AboutComponent } from './about/about.component';
import { ContactComponent } from './contact/contact.component';

const routes: Routes = [
  { path: '', redirectTo: '/home', pathMatch: 'full' }, // Redirect to home
  { path: 'home', component: HomeComponent },
  { path: 'about', component: AboutComponent },
  { path: 'contact', component: ContactComponent },
  { path: '**', redirectTo: '/home' } // Wildcard route for a 404 page
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule]
})
export class AppRoutingModule { }
```

### Explanation of Route Properties

- **path:** The URL path that the router will match.
- **component:** The component that will be rendered when the route is activated.
- **redirectTo:** Redirects to a specified route when the path matches.
- **pathMatch:** Determines how the router should match the URL segment (e.g., `full` or `prefix`).
- **Wildcard Route:** A catch-all route for handling unknown paths (404).

## 3. Adding Router Outlet

In your main application component (e.g., `app.component.html`), add a `<router-outlet>` directive. This is where the routed components will be displayed.

```html
<router-outlet></router-outlet>
```

## 4. Navigating Between Routes

You can navigate between routes using the `Router` service or by using the `<a>` tag with Angular’s router directives.

### Example of Using RouterLink in HTML

```html
<nav>
  <ul>
    <li><a routerLink="/home">Home</a></li>
    <li><a routerLink="/about">About</a></li>
    <li><a routerLink="/contact">Contact</a></li>
  </ul>
</nav>
```

### Example of Navigating Programmatically

You can also navigate programmatically using the `Router` service in your component.

```typescript
import { Component } from '@angular/core';
import { Router } from '@angular/router';

@Component({
  selector: 'app-header',
  templateUrl: './header.component.html'
})
export class HeaderComponent {
  constructor(private router: Router) {}

  goToHome() {
    this.router.navigate(['/home']);
  }
}
```

## 5. Route Parameters

You can pass parameters to your routes and retrieve them in your components.

### Define a Route with Parameters

```typescript
{ path: 'user/:id', component: UserComponent }
```

### Accessing Route Parameters in the Component

In the `UserComponent`, you can access the route parameters as follows:

```typescript
import { Component, OnInit } from '@angular/core';
import { ActivatedRoute } from '@angular/router';

@Component({
  selector: 'app-user',
  templateUrl: './user.component.html'
})
export class UserComponent implements OnInit {
  userId: string;

  constructor(private route: ActivatedRoute) {}

  ngOnInit() {
    this.route.params.subscribe(params => {
      this.userId = params['id'];
    });
  }
}
```

## 6. Lazy Loading Routes

Lazy loading allows you to load feature modules only when needed, improving performance.

### Example of Lazy Loading a Feature Module

1. **Generate a Feature Module**

   ```bash
   ng generate module feature --route feature --module app-routing
   ```

   This command creates a feature module and automatically configures lazy loading in `app-routing.module.ts`.

### Example of Lazy Loaded Route

```typescript
const routes: Routes = [
  { path: '', redirectTo: '/home', pathMatch: 'full' },
  { path: 'feature', loadChildren: () => import('./feature/feature.module').then(m => m.FeatureModule) }
];
```

## 7. Conclusion

You have now set up basic routing in your Angular application! This setup allows for component navigation, route parameters, and lazy loading. For more advanced routing features and configuration options, refer to the [official Angular documentation](https://angular.io/guide/router).

### Notes
- Make sure to replace component names and paths with the actual components used in your project.
- Adjust examples to suit your specific application requirements.
- Feel free to add more sections or examples as needed!