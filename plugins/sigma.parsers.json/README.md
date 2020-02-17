sigma.parsers.json
==================

Plugin developed by [Alexis Jacomy](https://github.com/jacomyal).

---

This plugin provides two functions: `sigma.parsers.json()` and `sigma.parsers.loadJSON()`. The first will load a JSON encoded file, parse it, and call `loadJSON()` which, eventually instantiate sigma and fill the graph with the `graph.read()` method. The main goal is to avoid using jQuery only to load an external JSON file.

The most basic way to use this helper is to call it with a path and a sigma configuration object. It will then instanciate sigma, but after having added the graph into the config object.

````javascript
sigma.parsers.json(
  'myGraph.json',
  { container: 'myContainer' }
);
````

Or passing a JSON already loaded in-memory to loadJSON:

````javascript
sigma.parsers.loadJSON(
  {
    nodes: [],
    edges: []
  },
  { container: 'myContainer' }
);
````


It is also possible to update an existing instance's graph instead.

````javascript
sigma.parsers.json(
  'myGraph.json',
  myExistingInstance,
  function() {
    myExistingInstance.refresh();
  }
);
````
