# Docker Image with Chrome, Node, and Yarn

This image adds Chrome Stable and an additional set of Chromium dependencies on top of the [node:8](https://hub.docker.com/_/node/) image which provides `node`, [`npm`](https://www.npmjs.com/), and [`yarn`](https://yarnpkg.com).

The Chromium dependencies added are based on what's [recommended](https://github.com/GoogleChrome/puppeteer/blob/master/docs/troubleshooting.md) for [puppeteer](https://github.com/GoogleChrome/puppeteer). This image doesn't provide puppeteer; however, because `npm` and `yarn` are available, it's one step away: `yarn add puppeteer`.

The Chrome binary can be referenced via `$CHROME_BIN`.
