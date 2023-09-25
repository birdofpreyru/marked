<a href="https://marked.js.org">
  <img width="60px" height="60px" src="https://marked.js.org/img/logo-black.svg" align="right" />
</a>

# Marked (Unofficial Build for Older Environments)

[![Latest NPM Release](https://img.shields.io/npm/v/@dr.pogodin/marked.svg)](https://www.npmjs.com/package/@dr.pogodin/marked)
[![NPM Downloads](https://img.shields.io/npm/dm/@dr.pogodin/marked.svg)](https://www.npmjs.com/package/@dr.pogodin/marked)
[![CircleCI](https://dl.circleci.com/status-badge/img/gh/birdofpreyru/marked/tree/master.svg?style=shield)](https://app.circleci.com/pipelines/github/birdofpreyru/marked)
[![GitHub Repo stars](https://img.shields.io/github/stars/birdofpreyru/marked?style=social)](https://github.com/birdofpreyru/marked)
[![Dr. Pogodin Studio](.README/logo-dr-pogodin-studio.svg)](https://dr.pogodin.studio)

> _This is an unofficial fork of [marked](https://www.npmjs.com/package/marked)
> library, built for ES2017 target, instead of ES2022, thus supporting older
> environments. Otherwise, it is an exact copy of the upstream. It is published
> to NPM as [@dr.pogodin/marked](https://www.npmjs.com/package/@dr.pogodin/marked)._

**&mdash; BELOW THIS POINT IS THE ORIGINAL MARKED DOCUMENTATION &mdash;**

- ⚡ built for speed
- ⬇️ low-level compiler for parsing markdown without caching or blocking for long periods of time
- ⚖️ light-weight while implementing all markdown features from the supported flavors & specifications
- 🌐 works in a browser, on a server, or from a command line interface (CLI)

## Demo

Checkout the [demo page](https://marked.js.org/demo/) to see marked in action ⛹️

## Docs

Our [documentation pages](https://marked.js.org) are also rendered using marked 💯

Also read about:

* [Options](https://marked.js.org/#/USING_ADVANCED.md)
* [Extensibility](https://marked.js.org/#/USING_PRO.md)

## Compatibility

**Node.js:** Only [current and LTS](https://nodejs.org/en/about/releases/) Node.js versions are supported. End of life Node.js versions may become incompatible with Marked at any point in time.

**Browser:** Not IE11 :)

## Installation

**CLI:** 

```sh 
npm install -g marked
```

**In-browser:** 

```sh
npm install marked
```

## Usage

### Warning: 🚨 Marked does not [sanitize](https://marked.js.org/#/USING_ADVANCED.md#options) the output HTML. Please use a sanitize library, like [DOMPurify](https://github.com/cure53/DOMPurify) (recommended), [sanitize-html](https://github.com/apostrophecms/sanitize-html) or [insane](https://github.com/bevacqua/insane) on the *output* HTML! 🚨

```
DOMPurify.sanitize(marked.parse(`<img src="x" onerror="alert('not happening')">`));
```

**CLI**

``` bash
# Example with stdin input
$ marked -o hello.html
hello world
^D
$ cat hello.html
<p>hello world</p>
```

```bash
# Print all options
$ marked --help
```

**Browser**

```html
<!doctype html>
<html>
<head>
  <meta charset="utf-8"/>
  <title>Marked in the browser</title>
</head>
<body>
  <div id="content"></div>
  <script src="https://cdn.jsdelivr.net/npm/marked/marked.min.js"></script>
  <script>
    document.getElementById('content').innerHTML =
      marked.parse('# Marked in the browser\n\nRendered by **marked**.');
  </script>
</body>
</html>
```

## License

Copyright (c) 2011-2022, Christopher Jeffrey. (MIT License)
