# console.save

Extends the console object and allows you to save JSON to the client from the browser.  The way it works is it creates a phantom download link to a `Blob` of the JSON object and spoofs the user clicking it.  You can use it by copy and pasting the script into the console, or use it programmatically by including the file.

## Code Example
html
```html
<script scr="cs.js"></script>
```
js
```JavaScript
var data = { 
  hey: "yo",
  key: "value"
};

console.save(data, 'whatever.json');  // downloads `data`
```
