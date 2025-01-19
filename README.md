# jwplayer-scraper

This module helps you get the source URLs of the media that is added to the JW Player in the page/iframes using node.js

## Installation

This module can be installed via npm:

```sh
$ npm install --save jwplayer-scraper
```

## Usage

```js
var scraper = require("jwplayer-scraper");
```

### Functions

#### scraper.getMediaSources(URL, options)

- **URL:** URL of the page that needs to be scraped
- **options (optional):** For now, this can only contain an object with the _'jwplayerFilename'_ key. If it's not set, it will try to automatically locate the jwplayer.js file. (This is experimental)

```js
var scraper = require("jwplayer-scraper");

(async function() {
  var sources = await scraper.getMediaSources(
    "https://<URL_OF_THE_WEBSITE>/<PATH_TO_THE_PAGE>",
    {
      jwplayerFilename: "jwplayer.6.11.js"
    }
  );

  console.log(sources);
})();
```

or if you want to use it with _.then()_ instead of async/await:

```js
var scraper = require("jwplayer-scraper");

scraper
  .getMediaSources("https://<URL_OF_THE_WEBSITE>/<PATH_TO_THE_PAGE>")
  .then(sources => {
    console.log(sources);
  });
```
