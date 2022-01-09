# indigo

Indigo is a 165 byte implementation of observables. An observable is a variable which notifies you whenever its value changes. Here's a simple example

```js
import { observe } from 'indigo'

// create a new observable

const name = observe('Alice')

// subscribe to changes

name.changed(value => 
  console.log(`name was changed to ${value}`)
)

```

When `name` is changed, the subscriber is notified:

```js
name('Sam') // set to a different value

// "name was changed to Sam" output to console
```

## API

### `indigo.observe( value )`

Creates a new observable who's value is initially set to `value`.

* value: `Object`
* returns `Observable`


### `Observable ( value )`

Changes an observable's value. All subscribers are notified about the change.

* value: `Object`
* returns nothing

### `Observable ()`

Returns an observable's current value.

* returns `Object`
