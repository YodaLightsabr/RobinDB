# RobinDB
A quick database for Node.js
## About RobinDB
RobinDB is a quick database for Node.js. It is built on top of [NeDB](https://github.com/louischatriot/nedb/) and meant to be a quicker and more reliable version of [Quick.db](https://github.com/lorencerri/quick.db). RobinDB also has a [cloud server](https://npmjs.com/package/robindb-server) as well as a [client](https://npmjs.com/package/robindb-client). This package is for a local database.

## Demonstration
```js
const db = require('robindb');
db.set('money', 50).then(() => {
  db.get('money').then(money => {
    console.log(money); // 50
    db.set('items', [
      'sword',
      'armor'
    ]).then(() => {
      db.get('*').then(allItems => {
        console.log(allItems); // { money: 50, items: [ 'sword', 'armor' ] }
      });
    });
  });
});
```

## Is RobinDB right for you?
If you're looking for a database that's:
 - Lightweight and simple
 - Easy to set up
 - Lightning fast
 - Cloud ready
 - Key/value JSON-based
 - 50x faster than Quick.db

...**RobinDB is for you**.

If you're looking for a database that's:
 - Built for lots of data storage
 - Has heavy permissions management
 - SQL or NoSQL

...**RobinDB is *not* for you.**

## Documentation

### `Robin.get(key)`
Get a key in the database
 - `key` - The key to get. If getting a key nested inside of objects, use dot notation. Required

returns `Promise<any>`

### `Robin.set(key, value)`
Set a key in the database
 - `key` - The key to set. If setting a key nested inside of objects, use dot notation. Required
 - `value` - The value to set the key to. Required

returns `Promise<Number>`

### `Robin.push(key, value)`
Push a value to an array. The value at the specified key must be an array. Ognom will not create an array for you.
 - `key` - The key of the array to push to. If pushing to a key inside of objects, use dot notation. Required
 - `value` - The value to push to the array. Required

returns `Promise<Number>`


### `Robin.delete(key)`
 - `key` - The key to delete. If deleting a key nested inside of objects, use dot notation. Required

returns `Promise<Number>`

That's it! If you have any questions I'm [YodaLightsabr#6565 on Discord](https://discord.gg/M8YY32acjm).
