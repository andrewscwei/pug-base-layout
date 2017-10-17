# pug-base-layout

This is a basic extensible Pug layout.

## Usage

```sh
$ npm install pug-base-layout
```

In your Pug layout:

```pug
extend <node_modules_path>/pug-base-layout/index
```

## Blocks

There are some blocks you can inherit/extend to customize the layout to your needs.

### `block config`

This block defines all config properties. Append to it in your derived layout to override certain properties.

### `block vars`

Override this block to add your own local variables.

### `block meta`

Override this block to add more meta tags to the `<head>` tag.

### `block styles`

Override this block to add additional styles (i.e. `<link/>`) to the `<head>` tag.

### `block scripts`

Override this block to add additional scripts (i.e. `<script/>`) to the end of the `<body>` tag.

### `block body`

Override this block to add content to the `<body>` tag.

## Configurations

All configurable variables are in the `config` block:

```js
// Indicates whether NODE_ENV is `development`
// @type {boolean}
$debug = process.env.NODE_ENV === `development`

// Override this to set the name of the entire app. This is used for mobile
// devices and OpenGraph. Note that this is not the same as `$title`.
// @type {string}
// @required
$appName = `UNTITLED`

// Override this to set the title of the page (this is not the same as
// `$appName`).
// @type {string}
// @required
$title = `UNTITLED`

// URL of this app, used for OpenGraph.
// @type {string}
// @optional
$url = undefined

// Content of the `viewport` meta tag. If evaluates to `false`, the meta tag
// will not be included.
// @type {string}
// @optional
$viewport = `width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover`

// Content of the `viewport` meta tag. If evaluates to `false`, the meta tag
// will not be included.
// @type {string}
// @optional
$description = undefined

// Content of the `viewport` meta tag. If evaluates to `false`, the meta tag
// will not be included.
// @type {string}
// @optional
$keywords = undefined

// Google Analytics ID (i.e. UA-XXXXXXXX-1).
// @type {string}
// @optional
$analytics = undefined

// Typekit ID (i.e. abc1def).
// @type {string}
// @optional
$typekit = undefined

// List of body classes.
// @type {string[]}
// @optional
$bodyClass = undefined

// Function to load manifest files. By default it just returns the passed in
// path prefixed with `/`.
// @type {Function}
// @optional
$manifestPath = (path) => `/${path}`
```

## Meta Tags and Manifest Files

This layout handles all the essential meta tags for you. Use this [H5BP favicon and app icon template](https://littlewebgiants.com/favicon-and-app-icon-template/) to generate your manifest files. This layout assumes you have the following files somewhere (you can configure the path):

- `favicon.png`
- `og-image.png`
- `manifest.json`
- `apple-touch-icon-180x180-precomposed.png`
- `apple-touch-icon-152x152-precomposed.png`
- `apple-touch-icon-144x144-precomposed.png`
- `apple-touch-icon-120x120-precomposed.png`
- `apple-touch-icon-114x114-precomposed.png`
- `apple-touch-icon-76x76-precomposed.png`
- `apple-touch-icon-72x72-precomposed.png`
- `apple-touch-icon-60x60-precomposed.png`
- `apple-touch-icon-57x57-precomposed.png`
- `apple-touch-icon-precomposed.png`
- `apple-touch-icon-144x144-precomposed.png`
- `browserconfig.xml`


## License

This software is released under the [MIT License](http://opensource.org/licenses/MIT).