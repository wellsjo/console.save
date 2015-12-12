# console.save
This script extends the `console` object in the browser and allows you to save JSON objects to your desktop.  I find this to be very useful for web scraping.

The way it works is it creates a phantom download link to a `Blob` of the JSON object and spoofs the user clicking it.  You can use it by copy and pasting the script into the console, or use it programmatically by including the file.

## Example
Console
```JavaScript
// paste cs.js in here to gain access to console.save

var data = { 
  foo: "bar",
  baz: "qux"
};

console.save(data, 'data.json');
```
data.json
```json
{
  "foo": "bar",
  "baz": "qux"
}
```
