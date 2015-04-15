extend-json ![Build status](https://travis-ci.org/wmonk/extend-json.svg?branch=master)
===========

`extend-json` is a npm module for populating JSON files, with other JSON files or a specified function.<br/>
Looks for pointer key with a path value. Keys need to be unique.
```
">>fileB": "./fileB.json"
```

```
var Promise = require('bluebird');
var extendJSON = require('./index');
var fileA = require('./fileA.json');

extendJSON(fileA).then(function (json) {
   console.log(JSON.stringify(json, null, 4))
}).catch(function (e) {
    console.log('error', e);
});
```

Options are optional and default to
```
extendJSON(fileA, {pointer:'>>', path:'./'})
```

