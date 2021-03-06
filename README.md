JavaScript LocalStorage Handler
===========================

A simple, library independent constructor for easing HTML5 LocalStorage API handling with JavaScript.

It extends the native LocalStorage API methods allowing for object and array saving and retrieving, returning useful information when called and some more awesomeness.

*This is my first repo, so any criticism would be appreciated.*

## Usage
```js
var lsh = new LocalStorageHandler();
console.log(lsh.set('fruit', 'orange')); // 'orange'
console.log(lsh.set('person', {name: 'Bob', age: 27})); // {name: 'Bob', age: 27}
console.log(lsh.key(0)); // 'fruit'
console.log(lsh.get('person')); // {name: 'Bob', age: 27}
console.log(lsh.data()); // [['fruit', 'orange'], ['person', {name: 'Bob', age: 27}]]
console.log(lsh.length); // 2
console.log(lsh.remove(3)); // false
console.log(lsh.remove('person')); // true
console.log(lsh.length); // 1
console.log(lsh.data()); // [['fruit', 'orange']]
console.log(lsh.clear()); // 1
```

## Base constructor

### `LocalStorageHandler`
Extends the `window.localStorage` API.

#### Public Methods

#### `LocalStorageHandler.get(key)`

Extends the native `window.localStorage.getItem()` method allowing for object and array retrieving.

#### `LocalStorageHandler.set(key, val)`

Extends the native `window.localStorage.setItem()` method allowing for object and array saving, plus returning the saved element.

#### `LocalStorageHandler.key(index)`

Extends the native `window.localStorage.key()` method stricting its usage for indexes only.

#### `LocalStorageHandler.data()`

Implements a method which returns a multidemensional array containing all of the items once saved on the LocalStorage (key-value pairs).

#### `LocalStorageHandler.remove(key|index)`

Extends the native `window.localStorage.remove()` method allowing for deletion based on index number as well. Returns true if the key was found before deletion, false if not.

#### `LocalStorageHandler.clear()`

Extends the native `window.localStorage.clear()` method returning the total of items cleared.

## TODO

* Implement the events handling via callback - see http://diveintohtml5.info/storage.html#storage-event
* Testing with all major browsers

## License

Creative Commons Attribution 3.0
