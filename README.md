# User
User configuration for Sublime text 3 (Linux)

## Repl [js]
if **repl js** gives the following error at launch:

```javascript
readline.js:220
    throw new TypeError('stringToWrite must be a string');
          ^
TypeError: stringToWrite must be a string
    at REPLServer._writeToOutput (readline.js:220:11)
    at REPLServer.Interface.prompt (readline.js:188:10)
    at REPLServer.displayPrompt (repl.js:400:8)
    at new REPLServer (repl.js:330:8)
    at Object.exports.start (repl.js:339:14)
    at C:\Users\Administrator\AppData\Roaming\Sublime Text 3\Packages\SublimeREPL\config\NodeJS\repl.js:5:20
    at Object.<anonymous> (C:\Users\Administrator\AppData\Roaming\Sublime Text 3\Packages\SublimeREPL\config\NodeJS\repl.js:38:3)
    at Module._compile (module.js:460:26)
    at Object.Module._extensions..js (module.js:478:10)
    at Module.load (module.js:355:32)

***Repl Closed***
```
try to update the [path to Sublime Text]/Packages/SublimeREPL/config/NodeJS/repl.js config file with this new variable **rep**.
```javascript
var rep = repl.start({
        prompt:    '> ', //null,
        source:    null, //process.stdin,
        eval:      null, //require('vm').runInThisContext,
        useGlobal: true, //false
        useColors: false
    });
```
