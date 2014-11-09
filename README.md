##Save JS console output to json file

Add console.save to your console object.  console.save(object, filename) will create a file of the object you save, and immediately download it to the filename you specify.  I find this useful for a number of things.

Example:
```JavaScript
var data = { 
  hey: "yo",
  key: "value"
};

// this automatically downloads/formats the "data" object to "whatever.json"
console.save(data, 'whatever.json'); 
```
