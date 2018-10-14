# Docker Image with Chrome, Node, Yarn, and AWS CLI

This image builds on top of the [`selenium/standalone-chrome`](https://hub.docker.com/r/selenium/standalone-chrome/) image, adding the following:

* [`node`](https://nodejs.org) (currently 8 LTS)
* [`npm`](https://www.npmjs.com/)
* [`yarn`](https://yarnpkg.com)
* [`awscli`](https://aws.amazon.com/cli/)
* [`jq`](https://stedolan.github.io/jq/)
* And an additional set of Chromium dependencies

The exact binary versions provided with each release are available in their corresponding release notes.

The Chromium dependencies mentioned above are based on what's [needed to run `puppeteer`](https://github.com/GoogleChrome/puppeteer/blob/master/docs/troubleshooting.md). However, it's worth noting that in my testing, the `['--no-sandbox', '--disable-setuid-sandbox']` flags are required to run it, which depending on your needs may or may not be acceptable. This image doesn't provide `puppeteer`, but because `npm` and `yarn` are available, it's one step away: `yarn add puppeteer`.

This image runs the container with a non-root user by default. The initial working directory is the user's home directory, which is exposed via the `$HOME` variable.

The Chrome binary path is exposed via the `$CHROME_BIN` variable.
