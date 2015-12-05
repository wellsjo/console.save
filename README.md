# console.save

Allows you to save json objects to disk from the browser console.

The way it works is it creates a phantom link to download a `Blob` of the json data, then creates a mouse event to click that link.

Example:
```JavaScript
var data = { 
  hey: "yo",
  key: "value"
};

// this automatically downloads/formats the "data" object to "whatever.json"
console.save(data, 'whatever.json'); 
```
