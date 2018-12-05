### SVG Sprites
================
## to install:
* `npm i -D svgo svg-sprite-generator`
* `npm run icons` to run script.

The buzz surrounding SVG has increased in the last few years, and for good reason. They are crisp on all devices, editable with CSS, and screen reader friendly. However, SVG editing software usually leaves extraneous and unnecessary code. Luckily, svgo can help by removing all of that (we'll install it below).

You can also automate the process of combining and spriting your SVGs to make a single SVG file [(more on that technique here)](https://css-tricks.com/svg-sprites-use-better-icon-fonts/). To automate this process, we can install [svg-sprite-generator](https://github.com/frexy/svg-sprite-generator).

npm i -D svgo svg-sprite-generator
The pattern is probably familiar to you now: once installed, add a task in your `package.json` scripts object:
`
"scripts": {
  ...
  "icons": "svgo -f src/images/icons &amp;&amp; mkdir -p dist/images && svg-sprite-generate -d src/images/icons -o dist/images/icons.svg"
}
`

Notice the icons task does three things, based on the presence of two && directives. First, we use svgo, passing a folder (-f flag) of SVGs; this will compress all SVGs inside the folder. Second, we'll make the dist/images folder if it doesn't already exist (using the mkdir -p command). Finally, we use svg-sprite-generator, passing it a folder of SVGs (-d flag) and a path where we want the SVG sprite to output (-o flag).
