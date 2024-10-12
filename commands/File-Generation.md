# File Generation

This document provides commands for generating different files in an Angular application using the Angular CLI.

## Generate a Component

Creates a new component along with its template, styles, and spec file.

```bash
ng generate component component-name
```

OR using shorthand:

```bash
ng g c component-name
```

### Options:
- `--inline-template`: Use inline template instead of a separate file.
- `--inline-style`: Use inline styles instead of a separate file.
- `--skip-tests`: Skip creating the spec file for unit tests.

---

## Generate a Standalone Component (Angular 14+)

Creates a standalone component that does not require a module declaration.

```bash
ng generate component component-name --standalone
```

---

## Generate a Service

Creates a new service for dependency injection.

```bash
ng generate service service-name
```

OR using shorthand:

```bash
ng g s service-name
```

### Options:
- `--skip-tests`: Skip creating the spec file for unit tests.

---

## Generate a Module

Creates a new module, optionally with routing configured.

```bash
ng generate module module-name
```

OR using shorthand:

```bash
ng g m module-name
```

### Options:
- `--routing`: Creates a module with routing capabilities.
- `--flat`: Creates the module without a separate directory.

---

## Generate a Directive

Creates a new directive.

```bash
ng generate directive directive-name
```

OR using shorthand:

```bash
ng g d directive-name
```

### Options:
- `--skip-tests`: Skip creating the spec file for unit tests.

---

## Generate a Pipe

Creates a new pipe.

```bash
ng generate pipe pipe-name
```

OR using shorthand:

```bash
ng g p pipe-name
```

### Options:
- `--skip-tests`: Skip creating the spec file for unit tests.

---

## Generate a Guard

Creates a route guard to control access to routes.

```bash
ng generate guard guard-name
```

OR using shorthand:

```bash
ng g g guard-name
```

### Options:
- `--can-activate`: Generates a guard that can activate a route.
- `--can-deactivate`: Generates a guard that can deactivate a route.
- `--can-load`: Generates a guard that can load a module.

---

## Generate an Interceptor

Creates a new HTTP interceptor.

```bash
ng generate interceptor interceptor-name
```

OR using shorthand:

```bash
ng g i interceptor-name
```

### Options:
- `--skip-tests`: Skip creating the spec file for unit tests.

---

## Generate a Class

Creates a new TypeScript class.

```bash
ng generate class class-name
```

OR using shorthand:

```bash
ng g cl class-name
```

---

## Generate an Enum

Creates a new TypeScript enum.

```bash
ng generate enum enum-name
```

OR using shorthand:

```bash
ng g e enum-name
```

---

## Generate an Interface

Creates a new TypeScript interface.

```bash
ng generate interface interface-name
```

OR using shorthand:

```bash
ng g i interface-name
```

---

## Generate a Resolver

Creates a new route resolver.

```bash
ng generate resolver resolver-name
```

OR using shorthand:

```bash
ng g r resolver-name
```

### Options:
- `--skip-tests`: Skip creating the spec file for unit tests.

---

## Summary

The Angular CLI provides various commands for generating files, which helps streamline the development process and maintain consistency across the project. You can customize each command with options to fit your project's needs.

For more information, refer to the [Angular CLI documentation](https://angular.io/cli).