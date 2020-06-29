# cordova-plugin-memory-warning-ios-android

Cordova plugin to dispatch memory warnings to javascript.

## Installation
#### Automatically (CLI / Plugman)
cordova-plugin-memory-warning-ios-android  is compatible with Cordova Plugman, compatible with PhoneGap 3.0 CLI, here's how it works with the CLI:



```bash
phonegap local plugin add https://github.com/RahulCV/cordova-plugin-memory-warning
```
#### or with Cordova CLI, from npm:

```bash
 cordova plugin add cordova-plugin-memory-warning-ios-android
 cordova prepare

```

#### or with Ionic  CLI, from npm:

```bash
 ionic cordova plugin add cordova-plugin-memory-warning-ios-android
 ionic cordova prepare
```





## Usage iOS

```javascript
// listen for 'memorywarning' events
document.addEventListener('memorywarning', function () {
    // release memory
});

// because iOS has app specific memory warnings
// isMemoryUsageUnsafe method always returns false on iOS
```

## Usage Android

__NOTE:__ on Android, your app's MainActivity.java file will be modified to add hooks into Android memory warning events!

```javascript
// listen for 'memorywarning' events
// on android these are only dispatched for system level memory pressure
// see below for app specific memory pressure handling
document.addEventListener('memorywarning', function () {
    // release memory
});

// because android does not have app specific memory warnings
// you should manually check memory state before performing memory intensive operations
// executes a callback that resolves with boolean true when memory usage is at an unsafe level
// optionally pass a second callback for error handling
cordova.plugins.CordovaPluginMemoryWarning.isMemoryUsageUnsafe(function (result) {
    if (result) {
        // release memory
    }
}, function (error) {
    // handle errors
});

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)

```