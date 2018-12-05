There are three approaches that you may use:

* Use commands that run cross-platform: Many useful commands are common to Unix and Windows. If your scripts are simple, consider using those.
* Use node packages: You can use node packages like rimraf or cross-env instead of shell commands. And obviously, you can use these packages in JS files if your script is large and complex.
* Use [ShellJS](https://www.npmjs.com/package/shelljs): ShellJS is an npm package that runs Unix commands via Node. So this gives you the power to run Unix commands on all platforms, including Windows.
