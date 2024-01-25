# Pyright Browser

This package contains a browser compatible version of Pyright.
Most of these changes are forked from the [microbit-foundation](https://github.com/microbit-foundation/pyright) with a few additional fixes on top.

## Usage

After installing the package, a fully compiled worker with language server support will be available at 

```
./node_modules/@typefox/pyright-browser/dist/pyright.worker.js
```

You can initialize and run it using the following snippet:

```js
// Initialize the worker with the JavaScript file
const worker = new Worker('/public-path/pyright.worker.js');
// Send the `boot` request to the language server
// This starts the language server and a nested worker that performs the language analysis.
worker.postMessage({
    type: 'browser/boot',
    mode: 'foreground'
});
```
