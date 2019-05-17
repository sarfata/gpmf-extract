# GPMF extract

Finds the metadata track in GoPro (Hero5 and later) video files (or any other camera that implements the GPMF) and extracts it for later analysis and processing.

Accepts a File and returns a promise that resolves to Buffer.

```shell
$ npm i gpmf-extract
```

Use:

```js
const gpmfExtract = require('gpmf-extract');
let rawData;
gpmfExtract(file).then(rd => {
  rawData = rd;
  // Do what you want with the data
});
```

If using it in the browser, you must specify it in the second argument. Optionally, you can also pass a second argument with a function to run when the processed percentage updates.

```js
const gpmfExtract = require('gpmf-extract');
const progress = percent => console.log(`${percent}% processed`);
let rawData;
gpmfExtract(file, true, progress).then(rd => {
  rawData = rd;
  // Do what you want with the data
});
```

Once extracted, you can process the data with [gopro-telemetry](https://github.com/JuanIrache/gopro-telemetry).

This code was created for the [GoPro Telemetry Extractor](https://tailorandwayne.com/gopro-telemetry-extractor/).

Here's a [playlist with cool uses of the GoPro metadata ](https://www.youtube.com/watch?v=V4eJDQik-so&list=PLgoeWSWqXedK_TbrZXg7L926Kzb-g_CXz).

This project is possible thanks to the [gpmf-parser documentation](https://github.com/gopro/gpmf-parser), open sourced by GoPro.

## More creative coding

If you liked this you might like other [creative coding projects](https://tailorandwayne.com/coding-projects/).

## To-DO

- Export time data
- publish
- Extract from .mov?