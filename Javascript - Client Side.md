
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
