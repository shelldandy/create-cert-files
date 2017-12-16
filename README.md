# create-cert-files
Create self signed cert files to be used with webpack-dev-server or browsersync

## Usage with BrowserSync

```bash
npm install --dev create-cert-files browser-sync
```

```js
const fakeCert = require('create-cert-files')()
const browserSync = require('browser-sync')

browserSync.init({
  https: {
    key: fakeCert.key,
    cert: fakeCert.cert
  }
})
```

* Profit
