# ember-did-change-attrs [![Build Status](https://travis-ci.org/workmanw/ember-did-change-attrs.svg?branch=master)](https://travis-ci.org/workmanw/ember-did-change-attrs)

This addon is a WIP rethink of [ember-diff-attrs](https://github.com/workmanw/ember-diff-attrs) which offered a decorator style approach to this problem.

With `ember-did-change-attrs` we're going to solve the same problem using mixins instead of functions. The aim is to offer a simpler API which covers attribute change use cases that previously might have been solved using the [now deprecated `didReceiveAttrs` and `didUpdateAttrs` arguments](https://github.com/emberjs/rfcs/pull/191).

This API is still experimental, suggestions for improvements are encouraged and very much appreciated.

## Installation

`ember install ember-did-change-attrs`

## Usage

```js
import DidChangeAttrs from 'ember-did-change-attrs';

export default Ember.Component.extend(DidChangeAttrs, {
  didChangeAttrsConfig: {
    attrs: ['email']
  },

  didChangeAttrs(changes) {
    this._super(...arguments);

    if(changes.email) {
      let oldEmail = changes.email.previous,
          newEmail = changes.email.current;
      // Do stuff
    }
  }
});
```
ember-did-change-attrs
==============================================================================

[Short description of the addon.]


Compatibility
------------------------------------------------------------------------------

* Ember.js v3.24 or above
* Ember CLI v3.24 or above
* Node.js v12 or above


Installation
------------------------------------------------------------------------------

```
ember install ember-did-change-attrs
```


Usage
------------------------------------------------------------------------------

[Longer description of how to use the addon in apps.]


Contributing
------------------------------------------------------------------------------

See the [Contributing](CONTRIBUTING.md) guide for details.


License
------------------------------------------------------------------------------

This project is licensed under the [MIT License](LICENSE.md).
