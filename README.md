# @battis/webpack-typescript-spa

In `.npmrc`:

```
auto-install-peers = true
```

```bash
npm add -D @battis/webpack-typescript-spa@github:battis/webpack-typescript-spa
```

In `webpack.config.js`:

```js
const config = require('@battis/webpack-typescript-spa');

module.exports = config({ root: __dirname });
```

Configuration options include, with defaults:

```json
{
  root, // absolute path
  build: "build", // path relative to root
  bundle: "main", // string name
  entry: "./src/index.ts", // path relative to webpack.config.js
  publicPath: "/", // path to app in URL
  externals: {}, // https://webpack.js.org/configuration/externals/
  favicon: false // path relative to root to favicon folder (see below)
  appName: false // will default to bundle name if not supplied
}
```

If `favicon` is `false`, favicons will be igored. If it is set to a path relative to the `root` path, it will assume there is a directory with the following files, and use them to generate a SPA assets folder:

```
📂favicon
 ∟ 📄 logo.svg
 ∟ 📄 manifest.json
 ∟ 📄 mask.svg
 ∟ 📄 startup.svg
```

In `package.json`:

```json
{
  ...
  "scripts": {
    "clean": "rm -rf build",
    "serve": "npx webpack serve",
    "build": "npx webpack"
  }
  ...
}
```
