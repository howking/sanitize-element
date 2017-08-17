[![Build Status](https://travis-ci.org/howking/sanitize-element.svg?branch=master)](https://travis-ci.org/howking/sanitize-element)
[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://www.webcomponents.org/element/howking/sanitize-element)
![Polymer2.0](https://img.shields.io/badge/Polymer-2.0-blue.svg)
![ES6](https://img.shields.io/badge/es-6-red.svg)

# &lt;sanitize-element&gt;

Element wrapper for the [Sanitize.js](https://github.com/gbirke/Sanitize.js) library (a whitelist-based HTML sanitizer),
to use [`<marked-element>`](https://www.webcomponents.org/element/PolymerElements/marked-element).

<!--
```
<custom-element-demo>
  <template>
    <style>
      pre {
        padding: 16px;
        overflow: auto;
        line-height: 1.20;
        background-color: #f6f8fa;
        font-family: monospace;
        border-radius: 3px;
      }
    </style>
    <link rel="import" href="sanitize-element.html">
    <script src="https://cdn.rawgit.com/gbirke/Sanitize.js/master/lib/sanitize.js"></script>
    <link rel="import" href="../marked-element/marked-element.html">
    <dom-bind>
      <template is="dom-bind">
        <next-code-block></next-code-block>
      </template>
    </dom-bind>
  </template>
</custom-element-demo>
```
-->
```html
<style>
  .logo { width: 32px; }
</style>

<sanitize-element config='{
   "elements": ["img"],
   "attributes":{"img":["class","src"]},
   "protocols":{"img":{"src":["https"]}}
   }' sanitizer="{{sanitizer}}"></sanitize-element>

<marked-element sanitize sanitizer="[[sanitizer]]">
  <div slot="markdown-html"></div>
  <script type="text/markdown">
Markdown Image link `![image](url)`.

![WebComponents](https://www.polymer-project.org/images/logos/p-logo-192.png)

You can set `class` like `<img class="logo">` and remove other attributes (e.g. onclick).

<img class="logo"
     src="https://www.polymer-project.org/images/logos/p-logo-192.png"
     onclick="alert('WebComponents')">

Source block is escaped.

      <img class="logo"
           src="https://www.polymer-project.org/images/logos/p-logo-192.png"
           onclick="alert('WebComponents')">

  </script>
</marked-element>
```

Other config like this.

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
