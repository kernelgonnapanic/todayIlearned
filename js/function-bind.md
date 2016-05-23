## Problem:
Calling a function with a proper context.

## Solution:
ES7 and in fact Babel provide us an opportunity to use a new syntax for that.

Old approach:
```      
let uglyUrls = Array.prototype.map.call(document.querySelectorAll('a'), node => node.href);
```

New approach:
```
const {map} = Array.prototype.map;

let niceUrls = document.querySelectorAll('a')::map(node => node.href);
```
