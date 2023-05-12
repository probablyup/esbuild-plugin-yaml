# @probablyup/esbuild-plugin-yaml

Use YAML files as ES6 modules with `esbuild`, with watch mode support. This is a temporary fork of `esbuild-plugin-yaml` until this PR is merged: https://github.com/martonlederer/esbuild-plugin-yaml/pull/5

## Install

```sh
yarn add -D @probablyup/esbuild-plugin-yaml
```

or

```sh
npm i -D @probablyup/esbuild-plugin-yaml
```

## Usage

Add to your esbuild plugins list:

```js
const esbuild = require("esbuild");
const { yamlPlugin } = require("@probablyup/esbuild-plugin-yaml");

esbuild.build({
  ...
  plugins: [
    yamlPlugin()
  ]
  ...
});
```

## Options

You can add your own custom configuration of options to `@probablyup/esbuild-plugin-yaml`:

```js
yamlPlugin({
  // options
});
```

### `loadOptions`

LoadOptions by [`js-yaml`](https://www.npmjs.com/package/js-yaml).

### `transform`

A function which can mutate parsed YAML. It should return an `object` or `undefined` (that will make no changes to the parsed YAML).

```js
  transform(data, filePath) {
    // transform the yaml file
    // the file content will be in the "data" field
    // the file path will be in the "filePath" field
    return { filePath, data };
  }
```
