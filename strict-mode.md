###Strict Mode

JavaScript can be made little more strict by enabling the **strict mode**. **Strict mode** applies to _entire scripts_ or to _individual functions_.

To invoke strict mode for an entire script or individual function, use **'use strict';** before any other statements.

* Normally when you forget to put _var_ in front of variable, JavaScript quietly creates a global variable and uses that. In strict mode however, an error is reported.

* Strict mode makes assignments which would otherwise silently fail throw an exception. Any assignment that silently fails in normal mode (assignment to a non-writable property, assignment to a getter-only property, assignment to a new property on a non-extensible object) will throw exception in strict mode.

* Strict mode makes attempts to delete undeletable properties throw exception.
```
'use strict';
delete Object.prototype; //throws a TypeError
```

* Strict mode disallows giving a function multiple parameters with same name.

* The _'this'_ binding in Strict mode, holds the value of undefined in functions that are not called as methods. Without strict mode, JavaScript will happily continue working with global object, creating and reading global variables.
