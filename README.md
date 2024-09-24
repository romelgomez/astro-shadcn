# Astro Shadcn

ref: https://ui.shadcn.com/docs/installation/astro


## 0) add some Adapters to server-side rendering (SSR)

`pnpm astro add vercel`

ref: [Adapters](https://docs.astro.build/en/guides/server-side-rendering/#official-adapters)


## 1) Dependencies

- pnpm create astro@latest `Astro Starter Kit: Minimal`
- pnpm dlx astro add react
- pnpm dlx astro add tailwind


## 2) Create a styles/globals.css file in the src folder.

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

## 3) src/pages/index.astro

```astro
---
import '@/styles/globals.css'
---
```

## 4) astro.config.mjs

```js
export default defineConfig({
  integrations: [
    tailwind({
      applyBaseStyles: false,
    }),
  ],
})
```

## 5) tsconfig.json

```json
{
  "extends": "astro/tsconfigs/strict",
  "compilerOptions": {
    "jsx": "react-jsx",
    "jsxImportSource": "react",
    "baseUrl": ".",
    "paths": {
      "@/*": [
        "./src/*"
      ]
    }
  }
}
```

## 6) Run the shadcn init command to setup your project:

`pnpm dlx shadcn@latest init`

## 7) You can now start adding components to your project.


`pnpm dlx shadcn@latest add button`

