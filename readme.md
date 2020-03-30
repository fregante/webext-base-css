# webext-base-css [![][badge-gzip]][link-npm]

  [badge-gzip]: https://img.badgesize.io/fregante/webext-base-css/master/webext-base.css.svg?compression=gzip&label=gzipped
  [link-npm]: https://www.npmjs.com/package/webext-base-css

> Extremely minimal stylesheet/setup for Web Extensions’ options pages (also dark mode)

Together with some stylesheets included by the browsers, extends and improves the the `options_ui.chrome_style` setting, including Firefox.

## Install

[Download the stylesheet](https://raw.githubusercontent.com/fregante/webext-base-css/master/webext-base.css) manually or use npm:

```sh
npm install webext-base-css
```

## Usage

```html
<!-- The first one is included in Firefox. It doesn't hurt Chrome though, leave it there for both -->
<link rel="stylesheet" href="chrome://global/skin/in-content/common.css">
<link rel="stylesheet" href="webext-base.css">
<link rel="stylesheet" href="your-own-stylesheet-if-necessary.css">
```

Here's a minimal but full `options.html` example page:

```html
<!doctype html>
<meta charset="utf-8">
<title>Options</title>
<link rel="stylesheet" href="chrome://global/skin/in-content/common.css">
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

Don't forget to also use [webext-options-sync](https://github.com/fregante/webext-options-sync) to manage and autosave your extension's options.

## Related

* [webext-storage-cache](https://github.com/fregante/webext-storage-cache) - Map-like promised cache storage with expiration. Chrome and Firefox
* [webext-dynamic-content-scripts](https://github.com/fregante/webext-dynamic-content-scripts) - Automatically registers your content_scripts on domains added via permission.request
* [Awesome-WebExtensions](https://github.com/fregante/Awesome-WebExtensions) - A curated list of awesome resources for WebExtensions development.
