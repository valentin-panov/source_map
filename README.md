# Restrict the source map generation

[![Build status](https://ci.appveyor.com/api/projects/status/00hx1c2asx8i0w65?svg=true)](https://ci.appveyor.com/project/vapanov/source-map)

WEB VERSION: https://valentin-panov.github.io/source_map/

It's much easier to hunt a treasure if you have a map.

One day John found himself hopelessly lost. As panic set in, he stumbled upon a weathered map tucked beneath a moss-covered barrel. Determined to find his way, he studied the map intently and discovered a faint trail leading towards some intriguing place..

Did you ever try to investigate the JavaScript sources that are downloaded by the browser? They are often combined and minified to make delivering them from the server more efficient, and may entangled to be unlike the sources created by a developer.

In these situations, it’s much easier to debug the original source, rather than the source in the transformed state that the browser has downloaded.

A source map is a file that maps from the transformed to the original source, enabling the browser to reconstruct the original and present it in the debugger.

When we build a project with the default setting, or even if we intentionally turn the source maps on, the whole internet will know our application structure. You can check it here https://valentin-panov.github.io/source_map/. Just open DevTools=>Sources. The source code may be found here.

![](public/1.png)

To prevent such leaks, we need to turn off the source map before pushing the project into production. It may be done in the .env file or directly in the build call string.

```javascript
// package.json
...
"scripts": {
    "build": "GENERATE_SOURCEMAP=false react-scripts build",

```
![](public/2.png)

Store your map in a secure vault and put your feet up, John won't find your trail.