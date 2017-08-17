[![Build Status](https://travis-ci.org/howking/sanitize-element.svg?branch=master)](https://travis-ci.org/howking/sanitize-element)
[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://www.webcomponents.org/element/howking/sanitize-element)
![Polymer2.0](https://img.shields.io/badge/Polymer-2.0-blue.svg)
![ES6](https://img.shields.io/badge/es-6-red.svg)

# &lt;sanitize-element&gt;

Element wrapper for the [Sanitize.js](https://github.com/gbirke/Sanitize.js) library (a whitelist-based HTML sanitizer),
to use [`<marked-element>`](https://github.com/polymerelements/marked-element).

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
