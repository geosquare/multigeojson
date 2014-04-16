# multigeojson
Converts mutli parts geojson to many single part geojsons and vice-versa.

## Installation
```
npm install multigeojson
```

## Usage
```javascript
var multigeojson = require('multigeojson');
var manyGeojsons = multigeojson.explode( 
  {
	  "type": "MultiLineString", 
	  "coordinates": [
	    [[10, 10], [20, 20], [10, 40]], 
	    [[40, 40], [30, 30], [40, 20], [30, 10]]
	  ]
	}
);
// manyGeojsons: [{"type":"LineString","coordinates":[[10,10],[20,20],[10,40]]},{"type":"LineString","coordinates":[[40,40],[30,30],[40,20],[30,10]]}]

var singleGeojson = multigeojson.implode([{"type":"LineString","coordinates":[[10,10],[20,20],[10,40]]},{"type":"LineString","coordinates":[[40,40],[30,30],[40,20],[30,10]]}])

//singleGeojson: {"type":"MultiLineString","coordinates":[[[10,10],[20,20],[10,40]],[[40,40],[30,30],[40,20],[30,10]]]}
```
## License
This project is licensed under the terms of the MIT license.
