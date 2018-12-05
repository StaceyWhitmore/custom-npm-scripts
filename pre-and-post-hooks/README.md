Let’s look at our say-hello script again. Say we want to execute the command echo 'I run before say-hello' before say-hello and echo 'I run after say-hello' after say-hello. This is what your scripts object would look like:

`
"scripts": {
    "say-hello": "echo 'Hello World'",
    "presay-hello": "echo 'I run before say-hello'",
    "postsay-hello": "echo 'I run after say-hello'"
}
`
The “pre” and “post” before the script names tell npm to execute these before and after the script called say-hello respectively.

To run them with out cluttering up your console, try using the `--silent` flag 
`npm run --silent say-hello`
