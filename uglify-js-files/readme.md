
`"scripts": {
  ...
  "autoprefixer": "postcss -u autoprefixer -r dist/css/*"
}
`

This task says: Hey postcss, use (-u flag) autoprefixer to replace (-r flag) any `.css` files in `dist/css` with vendor prefixed code. That's it! Need to change the default browser support for autoprefixer? It's easy to add to the script:

`"autoprefixer": "postcss -u autoprefixer --autoprefixer.browsers '&gt; 5%, ie 9' -r dist/css/*"
`

"scripts": {
  ...
  "uglify": "mkdir -p dist/js && uglifyjs src/js/*.js -m -o dist/js/app.js"
}
One of the great things about npm scripts is that they are essentially an alias for a command line task that you want to run over and over. This means that you can use standard command line code right in your script! This task uses two standard command line features, mkdir and &&.

The first half of this task, mkdir -p dist/js says: Create a folder structure (mkdir), but only if it doesn't exist already (-p flag). Once that completes successfully, run the uglifyjs command. The && lets you chain multiple commands together, running each one sequentially if the previous command completes successfully.

The second half of this task tells uglifyjs to start with all of the JS files (`*.js`) in `src/js/`, apply the "mangle" command (-m flag), and output the result to `dist/js/app.js`. Once again, check the documentation for the tool in question for a full list of options.

Let's update our uglify task to create a compressed version of `dist/js/app.js`. Chain another uglifyjs command and passing the "compress" (-c) flag:
