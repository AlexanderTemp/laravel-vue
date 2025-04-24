### 24/04/2025

Se puede definir un layout global en inertia app revisar /js/app.ts

```typescript
import MainLayout from './layouts/MainLayout.vue';
createInertiaApp({
  resolve: (name) => {
    const pages = import.meta.glob<DefineComponent>('./pages/**/*.vue', { eager: true });
    const page = pages[`./pages/${name}.vue`];
    page.default.layout = page.default.layout || MainLayout;
    return page;
  },
});
```
