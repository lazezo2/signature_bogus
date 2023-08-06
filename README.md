# SignTok
Sign your TikTok urls easily.
This is a port of [tiktok-signature](https://github.com/carcabot/tiktok-signature) using JSDOM

This project allows signing TikTok urls without having to run a headless browser, which lowers ram usage a lot.

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://www.heroku.com/deploy/?template=https://github.com/pablouser1/SignTok)
## Installation
### Docker
```
docker pull ghcr.io/pablouser1/signtok:master
```

Now you can create a container with:
```
docker run --publish 8080:8080 ghcr.io/pablouser1/signtok:master
```
### Manual
```
yarn install
```

Now you can run the server with:
```
node api/index.js
```
## Usage
### Webserver
You can send a POST request to http://localhost:8080/signature with a raw/plain body containing the url

(Content-Type: text/plain)

If you plan to use the already deployed Vercel version, you should use https://signtok.vercel.app/api/signature

You can see some examples [here](https://github.com/pablouser1/SignTok/blob/master/examples)

### Cli
```
node local.js 'YOUR_URL_HERE'
```

### Library
```bash
npm install signtok
```

```javascript
const SignTok = require('signtok');

const signer = new SignTok();
console.log(signer.sign('URL_HERE'));
```

## TODO
* Typescript typing
* Publish to npm with Github Actions

## Credits
* @H1W0XXX for providing a working X-Bogus script
