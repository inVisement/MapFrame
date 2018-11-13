# MapFrame
MapFrame expands Map in JS to have functionalities similar to R and Python's Panda DataFrame

## Inspiration
ES6 provides Map to kinda implement hash tables. You can set and set (key, value) pairs. You can also define functions and properties like an object. Therefore, Map can store your data for fast access with get and set. And its properties can be your metadata. It is simple and beautiful.

    map = new Map()

    // Set and get DATA
    map.set('row1', {col1: 11, col2: 'my name', col3: '11-10-2018'})
    map.set('row2', {col1: 21, col2: 'your name', col3: '5-8-2018'})
    map.get('row2')[col1] // 21

    // set and get METADATA
    map.metrics = ['col1']
    map.date = ['col3']
    map.dimensions = ['col2']
    map.date // ['col3']

    // Filter of Data
    data = Array.from(map)
    data.filter([row, cols] => cols[map.date] > '4-3-2018')

    // to and from json for DATA and METADATA
    METADATA = JSON.stringify(map)
    DATA = JSON.stringify(data)

Now, we can expand Map functionality to behave like DataFrame in R or Python's Pandas by writing bunch of methods and wrappers.

## suggested APIs:

    frame = new MapFrame ({url, metrics, dimensions, id}, initialArray)
    frame.info({metrics, filter_ids, subset})
    frame.unfo({filter_ids})
    //frame.filter((val, id) => )
    //frame.map((val, id) => val)
    //frame.reduce((val, id) => )
    //frame.clean()
    //frame.reset()

## Example:
    var data_host = "http://127.0.01:8887/data/"
    url = data_host + "latest housing valuation.csv"
    id = 'Fips'
    frame = new MapFrame({id, url})

## How to contribute?
Add your suggested APIs. to the end of list. When completed implementation and test, uncomment it so we know what has been done.

## How to use?
import it (Node.js) or through script in browser. and use it.

## License
MIT: Use it. Change it. Expand it. Don't own it.
