### 24/04/2025

### Nota 1 - 24/04/2025

Se puede definir un layout global en inertia app revisar /js/app.ts

```typescript
import MainLayout from './layouts/MainLayout.vue'
createInertiaApp({
  resolve: (name) => {
    const pages = import.meta.glob<DefineComponent>('./pages/**/*.vue', { eager: true })
    const page = pages[`./pages/${name}.vue`]
    page.default.layout = page.default.layout || MainLayout
    return page
  },
})
```

### Nota 2 - 24/04/2025

Cuando se está usando watch en una dependencia, se puede también observar en el primer renderizado usando inmediate

```typescript
watch(
  appearance,
  () => {
    console.log(appearance.value)
    modes.value.forEach((mode) => {
      mode.check = mode.value === appearance.value
    })
  },
  { immediate: true },
)
```
