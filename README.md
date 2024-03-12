# Welcome to Remix + Vite!

# Steps

## Installation

```
mkdir my-remix-app
cd my-remix-app
npm init -y

# install runtime dependencies
npm i @remix-run/node @remix-run/react @remix-run/serve isbot@4 react react-dom

# install dev dependencies
npm i -D @remix-run/dev vite
```

## Vite config
```
touch vite.config.js
```

Since Remix uses Vite, you'll need to provide a Vite config with the Remix Vite plugin. Here's the basic configuration you'll need:
```
import { vitePlugin as remix } from "@remix-run/dev";
import { defineConfig } from "vite";

export default defineConfig({
  plugins: [remix()],
});
```

## Root Route

```jsx
import {
  Links,
  Meta,
  Outlet,
  Scripts,
} from "@remix-run/react";

export default function App() {
  return (
    <html>
      <head>
        <link
          rel="icon"
          href="data:image/x-icon;base64,AA"
        />
        <Meta />
        <Links />
      </head>
      <body>
        <h1>Hello world!</h1>
        <Outlet />

        <Scripts />
      </body>
    </html>
  );
}

```

## Build

```
npx remix vite:build
```

## Run

First you will need to specify the type in package.json as module so that remix-serve can run your app.

```
{
  "type": "module"
  // ...
}
```

Now you can run your app with `remix-serve`:
```
npx remix-serve build/server/index.js
```

---

## Development

Run the Vite dev server:

```shellscript
npm run dev
```

## Deployment

First, build your app for production:

```sh
npm run build
```

Then run the app in production mode:

```sh
npm start
```

Now you'll need to pick a host to deploy it to.

### DIY

If you're familiar with deploying Node applications, the built-in Remix app server is production-ready.

Make sure to deploy the output of `npm run build`

- `build/server`
- `build/client`
