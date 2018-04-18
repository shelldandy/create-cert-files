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

## Usage with webpack

```bash
npm install --save-dev create-cert-files
```

In your webpack.config.js
```js
const fakeCert = require('create-cert-files')(options)
const fs = require('fs')

module.exports = {
  devServer: {
    https: {
            key: fs.readFileSync(fakeCert.key),
            cert: fs.readFileSync(fakeCert.cert)
           }
    }
}
```

## options
### keyPath
Path of key file
### certPath
Path of cert file
### altNames
An array of subjectAltName
```js
[
    {
      // type 2 is DNS
      type: 2,
      value: 'localhost'
    },
    {
      // type 7 is IP
      type: 7,
      ip: '127.0.0.1'
    }
]
```

* Profit
