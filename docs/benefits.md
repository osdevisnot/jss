## Benefits of using JavaScript Style Sheets.

### Compared to regular CSS.

1. Scoped selectors.

  CSS has just one global namespace. It is impossible to avoid selector collisions in non-trivial applications. Naming conventions like BEM might help within one project, but will not when integrating third-party code. JSS generates unique class names by default when it compiles JSON representation to CSS.

1. True rules isolation.

  Scoped selectors are not enough. CSS has properties which are inherited automatically from the parent element, if not explicitely defined. Thanks to [jss-isolate](https://github.com/jsstyles/jss-isolate) plugin, JSS rules will not inherit properties.

1. Avoids specificity conflicts.
1. Source order independence.
1. Slow selectors.

  Because JSS rules are collision free, there is no need to write deeply netsted selectors. This leads to stable [performance](./performance.md) at scale.

1. Code reuse, expressiveness.

  CSS is limited to applying multiple selectors to the same node in its code reuse capabilities.
JSS allows you to compose rules from multiple sources. You can reuse existing rules, you can use functions to generate rules and to calculate values. This way we can avoid repeatitions in a very explicit way.

1. Refactoring.

  Thanks to javascript modules and explicit code reuse, we can quickly locate dependencies during refactoring.

1. Dead code elimination.
1. Vendor Prefixing.

  Using JSS [vendor-prefixer](https://github.com/jsstyles/jss-vendor-prefixer) plugin, prefixes added at runtime very efficiently, only for the required browser and do *not* increase download size.

1. Download size.

  JSS size is up to 50% smaller, you can save a bandwidth and increase site performance.

1. Code sharing

  You can easily share constants and functions between JS and CSS.

1. Adoption to environment

  You can generate styles according the environment requirements at runtime, for e.g. you can express any complex condition considering for e.g. pixel density, resolution and device type at the same time.
You can compose new style sheets based on settings and environment out of existing once.

### Compared to server-side preprocessing languages (stylus/less/sass and co.)

1. Aforementioned benefits
1. Just one language.

  There is no need to learn new preprocessing languages. They all come with a burden of a new syntax for variables, functions, mixins, extends and others. At the same time there is nothing they can do JavaScript can't.


### Compared to css-modules

1. Aforementioned benefits
1. Not yet another language

  JavaScript has got a w3c standard for modules, variables, functions, constants etc., while css-modules defines its own preprocessing language.

### Compared to inline styles

1. Easy rules caching.

  While payload caching for JS is the same as for CSS, there is a benefit of caching CSS Rules against inline styles. CSS rules are generated only once, they are static. Inline styles may change frequently, it is hard to ensure caching for them. JSS is generating regular CSS which results in the same static CSS Rules after it is rendered. Inline styles are more suitable for dynamic changes like animations.

1. All CSS features included.

  Unlike inline styles, JSS gives you all CSS features:
  - Media queries
  - Keyframes animation
  - Pseudo selectors
  - Fallbacks: you can define the same property [multiple times](./json-api.md#multiple-declarations-with-identical-property-names), like you know it from CSS.
  - Automatic vendor prefixing

1. Performance

Inline styles are [slower](./performance.md) than class names.

### Related articles:
https://byjoeybaker.com/react-inline-styles

https://medium.com/@dbow1234/component-style-b2b8be6931d3

More articles are welcome.