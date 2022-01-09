# indigo

Indigo is a 165 byte implementation of observables. An observable is a variable which notifies subscribers of value changes. Here's a simple example

```js
import { use } from 'indigo'

// create a new observable

const name = use('Alice')

// subscribe to changes

name.on(value => 
  console.log(`name was changed to ${value}`)
)

```

When `name` is changed, the subscriber is notified:

```js
name('Sam') // set to a different value

// "name was changed to Sam" output to console
```

## API

#### `indigo.use( value )`

Creates a new observable who's value is initially set to `value`.

* value: `Object`
* returns `Observable`


#### `indigo.using( dependencies..., function)`

Creates a new observable who's value is the result of `function()`. If an observable in `dependencies` changes, the new observable will change too and notify any subscribers.

* dependencies : `Array<Observable>` (splash argument)
* function : `Function`


#### `Observable()`

Returns an observable's current value.

* returns `Object`


#### `Observable( value )`

Changes an observable's value. All subscribers are notified about the change.

* value: `Object`
* returns nothing


#### `Observable.on( function )`

Subscribes a function to an observable. Whenever the observable's value changes, `function` will be called with the new value.

* function: `Function`
* returns nothing
