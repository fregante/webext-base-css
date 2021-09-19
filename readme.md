# webext-base-css [![][badge-gzip]][link-npm]

[badge-gzip]: https://img.badgesize.io/fregante/webext-base-css/master/webext-base.css.svg?compression=gzip&label=gzipped
[link-npm]: https://www.npmjs.com/package/webext-base-css

> Extremely minimal "native" stylesheet/setup for Web Extensions’ options pages (also dark mode)

Together with some stylesheets included by the browsers, extends and improves the the `options_ui.chrome_style` setting, including Firefox.

It's meant to look as _native_ as possible, _invisible_. `webext-base-css` is what browsers should offer by default.

Look at the demo [options.html](options.html) for the suggested markup (it's basic and not really enforced.)

| Demo: Chrome with light theme | Firefox with dark theme |
| --- | --- |
| ![white](https://user-images.githubusercontent.com/1402241/77975846-8ca1e780-72fb-11ea-8e02-33ab27746beb.png) | ![black](https://user-images.githubusercontent.com/1402241/77975849-8d3a7e00-72fb-11ea-8474-4f8b1f83d6c5.png) |

## Install

[Download the stylesheet](https://raw.githubusercontent.com/fregante/webext-base-css/master/webext-base.css) manually or use npm:

```sh
npm install webext-base-css
```

## Usage

```html
<link rel="stylesheet" href="webext-base.css">
<link rel="stylesheet" href="your-own-stylesheet-if-necessary.css">
```

You'll also have to set `chrome_style: true` in your manifest.json:

```json
{
	"options_ui": {
		"page": "options.html",
		"chrome_style": true
	}
}
```

💡 Tip: Also use [webext-options-sync](https://github.com/fregante/webext-options-sync) to manage and autosave your extension's options.

### Usage with a bundler

Depending on how your bundler is configured, you might be able to use one of these to import the module directly from `node_modules`. If you have issues or have a better solution, please send a PR or open an issue.

```html
<!-- From options.html -->
<link rel="stylesheet" href="./node_modules/webext-base-css/webext-base.css">
```

```js
// From options.js
import 'webext-base-css';
```

```css
/* From options.css or .scss */
@import 'webext-base-css';
@import '~webext-base-css';
@import '~webext-base-css/webext-base.css';
@use 'webext-base-css';
```

### Full example

Here's a minimal but full `options.html` example page:

```html
<!doctype html>
<meta charset="utf-8">
<title>Options</title>
<link rel="stylesheet" href="webext-base.css">
<link rel="stylesheet" href="options.css">
<form>
	<p>
		<label for="name">Name</label><br>
		<input type="text" id="name" name="name" spellcheck="false" autocomplete="off" required/>
	</p>
	<p>
		<label>
			<input type="checkbox" name="logging">
			Show the features enabled on each page in the console
		</label>
	</p>
</form>
<script src="options.js"></script>
```

## Related

- [webext-storage-cache](https://github.com/fregante/webext-storage-cache) - Map-like promised cache storage with expiration. Chrome and Firefox
- [webext-dynamic-content-scripts](https://github.com/fregante/webext-dynamic-content-scripts) - Automatically registers your content_scripts on domains added via permission.request
- [Awesome-WebExtensions](https://github.com/fregante/Awesome-WebExtensions) - A curated list of awesome resources for WebExtensions development.
- [More…](https://github.com/fregante/webext-fun)
