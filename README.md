# Docker Image with Chrome, Node, and Yarn

This image adds [`node`](https://nodejs.org) (currently 8 LTS), [`npm`](https://www.npmjs.com/), [`yarn`](https://yarnpkg.com), and an additional set of Chromium dependencies on top of the [`selenium/standalone-chrome`](https://hub.docker.com/r/selenium/standalone-chrome/) image, which provides Chrome.

The Chromium dependencies added are based on what's [needed to run `puppeteer`](https://github.com/GoogleChrome/puppeteer/blob/master/docs/troubleshooting.md). However, it's worth noting that at this time the `['--no-sandbox', '--disable-setuid-sandbox']` flags are required to run it, which depending on your needs may or not be acceptable. This image doesn't provide puppeteer, but because `npm` and `yarn` are available, it's one step away: `yarn add puppeteer`.

The Chrome binary can be referenced via `$CHROME_BIN`.
