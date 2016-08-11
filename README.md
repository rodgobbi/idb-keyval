# IDB-Keyval

This is a super-simple-small promise-based keyval store implemented with IndexedDB, largely based on [async-storage by Mozilla](https://github.com/mozilla-b2g/gaia/blob/master/shared/js/async_storage.js).

If you're looking for a more general-purpose promise-based IDB, try [IDB on NPM](https://www.npmjs.com/package/idb). If you want to support older browsers with broken/absent IDB implementations, try [localForage](https://github.com/localForage/localForage). 

## Usage

### Setting:

```js
idbKeyval.set('hello', 'world');
```

Since this is IDB-backed, you can also store numbers, arrays, objects and blobs. All methods return promises:

```js
idbKeyval.set('hello', 'world')
  .then(() => console.log('It worked!'))
  .catch(err => console.log('It failed!', err));
```

### Getting:

```js
// logs: "world"
idbKeyval.get('hello').then(val => console.log(val));
```

### Removing:

```js
idbKeyval.remove('hello');
```

### Clearing:

```js
idbKeyval.clear();
```

That's it!