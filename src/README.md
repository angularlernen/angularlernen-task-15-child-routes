Child routes
============

### Introduction

Let's make each _feature module_ (`events` and `profiles`) responsible for it's own routes.

### Task

1. Make sure that each feature module has a starting component (`EventsComponent` respectively `ProfilesComponent`).

2. Make sure, each of this components as mentioned in 1 has `<router-component></router-component>` located inside.

3. It's a good practice to move all files from the `events/events` component folder directly into its module folder. The same applies to the `profiles/profiles` component.

4. Move the feature specific routing configurations from `app-routing.module.ts` into `myfeature-routing.module.ts` (_myfeature_ here is either `events` or `profiles`).

5. For each feature module, the so called _feature path_ points to the starting component of this module. For this path (feature path) provide child configuration, with paths, relative to the feature path.

6. Make the decision which _feature_ should be _activated_ first, by redirecting to the according URL (within `app-routing.module.ts`.

### HOWTOs

#### app-routing.module.ts

```ts
const routes: Routes = [
  {
    path: '',
    pathMatch: 'full',
    redirectTo: '/events'
  }
];
```

#### events-routing.module.ts 

```ts
const routes: Routes = [
  {
    path: 'events',
    component: EventsComponent,
    children: [
      // TODO: add the relative configuration here
    ]
  }
];
```
