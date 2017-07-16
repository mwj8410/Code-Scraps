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
 
### Functions for getting all indexes for a spevific falue in a string
```javascript
const indexOfAll = (str, term) => {
  let indexes = [];
  let result = str.indexOf(term);

  while (result > -1) {
    // Check for escaping
    if (str[result - 1] !== '\\') {
      indexes.push(result);
    }
    result = str.indexOf(term, result + 1);
  }

  return indexes;
}
```
