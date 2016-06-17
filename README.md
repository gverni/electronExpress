# electronExpress
Sample electron application that run express. It's based on electron version 1.2.0 and express 4.14.0. 

After you've cloned/downaloded the repository, use the following command to install dependencies and run the app: 

```
 npm install && npm start
```

## How to recreate the same app 
To re-create similar application use the following steps: 

```
# Clone the electroni-quick-start repository
git clone https://github.com/electron/electron-quick-start
# Go into the repository
cd electron-quick-start
# Install dependencies 
npm install && npm start
# Add electron-rebuild (see http://electron.atom.io/docs/tutorial/using-native-node-modules/)
npm install --save-dev electron-rebuild 
# Add express 
npm install --save-dev express
# Rebuild electron 
./node_modules/.bin/electron-rebuild
```
Once you have done that, edit the main.js and include express: 

  ```js
var express = require('express')
var server = express()

server.get('/', function (req, res) {
  res.send('Hello World from Express executed in electron!');
});

server.listen(3000, function () {
  console.log('Express running in electron and listening on port 3000!');
});
  ```
Add loading of the root of express into main.js: 

```js
  // Comment this:
  // mainWindow.loadURL('file://${__dirname}/index.html')
  mainWindow.loadURL('http://127.0.0.1:3000')
  ```

Execute electron app
```
 npm start
```
