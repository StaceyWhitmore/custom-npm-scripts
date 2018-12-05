Serve and Automatically Inject Changes with BrowserSync
=========================================================
One of the last pieces to the puzzle is BrowserSync. A few of the things it can do: start a local server, automatically inject updated files into any connected browser, and sync clicks & scrolls between browsers. Install it and add a task:

`npm i -D browser-sync`

`
"scripts": {
  ...
  "serve": "browser-sync start --server --files 'dist/css/*.css, dist/js/*.js'"
}
`
Our BrowserSync task starts a server (--server flag) using the current path as the root by default. The --files flag tells BrowserSync to watch any CSS or JS file in the `dist` folder; whenever something in there changes, automatically inject the changed file(s) into the page.

You can open multiple browsers (even on different devices) and they will all get updated file changes in real time!
