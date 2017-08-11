![Polymer2.0](https://img.shields.io/badge/Polymer-2.0-blue.svg)

# [WIP] &lt;sanitize-element&gt;

Element wrapper for the [Sanitize.js](https://github.com/gbirke/Sanitize.js) library.
work for [`<marked-element>`](https://github.com/polymerelements/marked-element).

> Waiting for merge [PolymerElements/marked-element#74](https://github.com/PolymerElements/marked-element/pull/74)

``` html
<sanitize-element config='{
  "elements":["a","img"],
  "attributes":{"a":["href","title"],"img":["src"]},
  "protocols":{"a":{"href":["http","https"]}}
  }' sanitizer="{{sanitizer}}"></sanitize-element>
<marked-element markdown="[[markdown]]" sanitize sanitizer="[[sanitizer]]">
```
