# TreeShakingPlayground

This project aims to demonstrate the effectiveness of tree shaking and optimized libraries.

## moment

The moment-pack project exclusively utilizes moment.js.

## date-fns

The date-fns-pack project exclusively utilizes date-fns.

## How to

Open two terminals

1.  To install and display date-fns-pack dependencies: `cd date-fns-pack && npm i && npm run bundle`
2.  To install and display moment-pack dependencies: `cd moment-pack && npm i && npm run bundle`

Two windows displaying dependencies should open.

## What to

The goal here is to demonstrate that moment is not being tree shaken. The only method used in our example is moment().toISOString();, yet the entire package is being included in the build. We have all the formatting for every country, even if we don't use them. This results in a package weighing 688kb for just 3 lines of code. That's a **monstrosity**.

If we compare with the date-fns package we're only at 5kb because the only method imported is the one we use.

The magic here is that date-fns is tree shaked, wich means if we simplify it that the library will only embed the method that wew really use in our bundle.

## More

- [Tree shaking explained](https://developer.mozilla.org/fr/docs/Glossary/Tree_shaking)
- [momentjs](https://momentjs.com/)
- [date-fns](https://date-fns.org/)
- [webpack-bundle-analyzer](https://www.npmjs.com/package/webpack-bundle-analyzer)
- [bundlephobia](https://bundlephobia.com/)
