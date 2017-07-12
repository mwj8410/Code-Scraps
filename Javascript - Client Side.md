
### Utility function to streamline hooking into global events in web browsers
```javascript
const addEvent = function(object, type, callback) {
  if (object === null || typeof(object) === 'undefined') return;
  if (object.addEventListener) {
    object.addEventListener(type, callback, false);
  } else if (object.attachEvent) {
    object.attachEvent("on" + type, callback);
  } else {
    object["on"+type] = callback;
  }
};
```

Usage:
```javascript
addEvent(window, 'resize', () => {
  console.log('hit');
});
```

### Functions for transforming an object name to a TitleCase string
```javascript
const camelCaseToTitleCase = (str) => str.match(/[A-Z]*[^A-Z]+/g)
		.map((word) => word.charAt(0).toUpperCase() + word.substr(1).toLowerCase())
		.join(' ')
 ```
 
 Usage:
 ```javascript
 camelCaseToTitleCase('camelCaseString')
 ```
 
