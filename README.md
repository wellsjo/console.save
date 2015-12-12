# console.save

Extends the console object and allows you to save JSON to the client from the browser.  The way it works is it creates a phantom download link to a `Blob` of the JSON object and spoofs the user clicking it.  You can use it by copy and pasting the script into the console, or use it programmatically by including the file.

## Code Example
Console
```JavaScript
var data = { 
  foo: "bar"
};

console.save(data, 'data.json');
```
data.json
```json
{
  foo: "bar"
}
```
