[![Build Status](https://travis-ci.org/howking/sanitize-element.svg?branch=master)](https://travis-ci.org/howking/sanitize-element)
[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://www.webcomponents.org/element/howking/sanitize-element)
![Polymer2.0](https://img.shields.io/badge/Polymer-2.0-blue.svg)
![ES6](https://img.shields.io/badge/es-6-red.svg)

# &lt;sanitize-element&gt;

Element wrapper for the [Sanitize.js](https://github.com/gbirke/Sanitize.js) library (a whitelist-based HTML sanitizer),
to use [`<marked-element>`](https://github.com/polymerelements/marked-element).

<!--
```
<base href="https://raw-dot-custom-elements.appspot.com/howking/sanitize-element/v0.1.1/sanitize-element/">
<!-- START-HIDDEN-SECTION: Add imports and styling here. -->
<script src="../webcomponentsjs/webcomponents-lite.js"></script>
<link rel="import" href="../marked-element/marked-element.html">
<script src="https://cdn.rawgit.com/gbirke/Sanitize.js/master/lib/sanitize.js"></script>
<link rel="import" href="sanitize-element.html">
<!-- END-HIDDEN-SECTION: Add the visible part of the demo below. -->
<dom-bind>
  <template is="dom-bind">
    <style>.logo { width: 32px; }</style>
    <sanitize-element config='{
                              "elements": ["img"],
                              "attributes":{"img":["class","src"]},
                              "protocols":{"img":{"src":["https"]}}
                              }' sanitizer="{{sanitizer}}"></sanitize-element>
    <marked-element sanitize sanitizer="[[sanitizer]]">
      <div slot="markdown-html"></div>
      <script type="text/markdown">
Markdown Link of image.

```html
![WebComponents](https://web-components-resources.appspot.com/static/logo.svg)
```
![WebComponents](https://web-components-resources.appspot.com/static/logo.svg)

You can set `class` like `<img class="logo">` and remove other attributes.

```html
<style>.logo { width: 32px; }</style>
<img class="logo" src="https://web-components-resources.appspot.com/static/logo.svg" onclick="alert('WebComponents')">
```
<img class="logo" src="https://web-components-resources.appspot.com/static/logo.svg" onclick="alert('WebComponents')">

Source block is escaped.

```
```html
<img class="logo" src="https://web-components-resources.appspot.com/static/logo.svg" onclick="alert('WebComponents')">
```
```
      </script>
</markd-element>
  </template>
</dom-bind>

```
-->

``` html
<sanitize-element config='{
  "elements":["a","img"],
  "attributes":{"__ALL__":["class"], "a":["href","title"], "img":["src"]},
  "protocols":{"a":{"href":["http","https"]}}
  }' sanitizer="{{sanitizer}}"></sanitize-element>
<marked-element markdown="[[markdown]]" sanitize sanitizer="[[sanitizer]]">
  <div slot="markdown-html"></div>
</markd-element>
```

Note: The `config` attribute must be double quoted JSON.
