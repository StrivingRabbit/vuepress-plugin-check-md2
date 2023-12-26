# vuepress-plugin-check-md2

> `vuepress check-md` - Check dead links of markdown.

**This plugin is powered by [check-md](https://github.com/whxaxes/check-md) made with ❤️ by [@whxaxes](https://github.com/whxaxes).**

## Features

This plugin help check following types of dead links

- Empty link.
- Non-existed target markdown file.
- Non-slugified hash.
- Non-existed hash.
- Prefer `.md` to `.html` (`warn`)

## Install

```bash
yarn add -D vuepress-plugin-check-md2
# OR npm install -D vuepress-plugin-check-md
```

## Usage

```javascript
module.exports = {
  plugins: ['check-md2']
}
```

```bash
vuepress check-md2 [docsDir]
```

### Passing Options

```javascript
module.exports = {
  plugins: ['check-md2', {
    pattern: '**/*.md'
  }]
}
```

## Options

Following options can also be passed via CLI options, e.g. `vuepress check-md2 --fix`

### fix

- Type: `boolean`
- Default: `false`

Check and try to fix

### pattern

- Type: `GlobPattern`
- Default: `**/*.md`

[Glob](https://github.com/isaacs/node-glob) pattern of resolved markdowns.

### ignore

- Type: `GlobPattern`
- Default: `**/node_modules`

[Glob](https://github.com/isaacs/node-glob) pattern to specify paths from being checked.

### exitLevel

- Type: `'none' | 'info' | 'warn' | 'error'`
- Default: `'error'`

Process exit level, default to `error`, other choice is warn and none, it will not exit if setting to none.

### filter

- TYpe: `Function`
- Default: `() => true`

Filter function to filter out some links.
