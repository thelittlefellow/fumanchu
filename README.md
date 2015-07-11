# fumanchu

Fumanchu is mustache fork with 2 small additions: {{@}} and {{?}} tags

## Traversal tag {{@}}

Mustache lacks object traversal, so it is not possible to have dynamic properties.
Only way to fight this is to use sections, ie. {{#section}} tag:

var data = {section: [{name: 'first', data: {..}}, {name: 'second', data: {...}}, ...]}

Fumanchu adds {{@}} tag that can be used with object, for example

var data = {list: {first: {a: 1, b: 2}, second: {a: 3, b: 4}, ...}};

If you want to traverse list, use {{@list}} in template:

{{@list}}a value is {{a}}, b value is {{b}},{{/list}}

Output:

a value is 1, b value is 2,a value is 3, b value is 4, ...

## Property name tag {{?}}

When inside {{@}} you can reference property name with {{?}}
Example:

var data = {list: {first: {a: 1, b: 2}, second: {a: 3, b: 4}, ...}};

Template:

{{@list}}current property is {{?}}, a value is {{a}}, b value is {{b}},{{/list}}

Output:

current property is first, a value is 1, b value is 2, current property is second, a value is 3, b value is 4,

Also, {{&}} can be used inside sections and it will expand to element index.

## Other

Fumanchu is compatible with mustache. More info on [mustache page](https://github.com/janl/mustache.js)
