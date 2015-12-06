# console.save

Extends the console object and allows you to save JSON to the client from the browser.  The way it works is it creates a phantom link to download a `Blob` of the json data, then creates a mouse event to click that link.
```JavaScript
var data = { 
  hey: "yo",
  key: "value"
};

console.save(data, 'whatever.json');  // downloads `data`
```
