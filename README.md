# React SSR Template

A production-ready template for building server-side rendered (SSR) React applications with Vite.

## Adding Packages

### Client

Add React or client-side libraries as regular `dependencies`:

```shell
npm install react
```

### Server

Add server-side packages (e.g., `express`) as `devDependencies`:

```shell
npm install express --save-dev
```

Then, include the package in the server build by updating the `tsup.config.ts`:

```ts
import { defineConfig } from 'tsup'

export default defineConfig({
  entry: ['server'],
  outDir: 'dist/server',
  target: 'node22',
  format: ['cjs'],
  clean: true,
  minify: true,
  external: ['lightningcss', 'esbuild', 'vite'],
  noExternal: ['express', 'sirv', 'compression'], // Include server packages here
})
```