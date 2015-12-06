# console.save

Extends the console object and allows you to save JSON to the client from the browser.  The way it works is it creates a phantom download link to a `Blob` of the JSON object and spoofs the user clicking it.

## Code Example
```html
<script scr="cs.js"></script>
```
```JavaScript
var data = { 
  hey: "yo",
  key: "value"
};

console.save(data, 'whatever.json');  // downloads `data`
```
## Script
You can paste this in the browser console as well.
```javascript
(function(console) {

  /**
   * Save json object to disk.
   *
   * @param {object} obj The object to save.
   * @param {string} filename The name of the file to save.
   */
  console.save = function(obj, filename) {

    if (!obj) {
      console.error('console.save: No data.');
      return;
    }

    if (filename == null) filename = 'console.json';

    if (typeof obj === 'object') {
      var data = JSON.stringify(obj, undefined, 4);
    }

    // create a phantom link element to download a Blob of data, then create
    // a mouse event to click the link to download the file.
    var blob = new Blob([data], {
      type: 'text/json'
    });
    var e = document.createEvent('MouseEvents');
    var a = document.createElement('a');

    a.download = filename;
    a.href = window.URL.createObjectURL(blob);
    a.dataset.downloadurl = ['text/json', a.download, a.href].join(':');
    e.initMouseEvent('click', true, false, window, 0, 0, 0, 0, 0, false, false, false, false, 0, null);
    a.dispatchEvent(e);
  };

})(console);
```
