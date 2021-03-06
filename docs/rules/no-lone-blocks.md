# Disallow Unnecessary Nested Blocks (no-lone-blocks)

In JavaScript, prior to ES6, standalone code blocks delimited by curly braces do not create a new scope and have no use. For example, these curly braces do nothing to `foo`:

```js
{
    var foo = bar();
}
```

In ES6, code blocks may create a new scope if a block-level binding (`let` and `const`), a class declaration or a function declaration (in strict mode) are present. A block is not considered redundant in these cases.

## Rule details

This rule aims to eliminate unnecessary and potentially confusing blocks at the top level of a script or within other blocks.

The following patterns are considered warnings:

```js
{}

if (foo) {
    bar();
    {
        baz();
    }
}

function bar() {
    {
        baz();
    }
}

{
    function foo() {}
}
```

The following patterns are not considered warnings:

```js
while (foo) {
    bar();
}

if (foo) {
    if (bar) {
        baz();
    }
}

function bar() {
    baz();
}

{
    let x = 1;
}

{
    const y = 1;
}

{
    class Foo {}
}

// In strict mode, with blockBindings: true
{
    function foo() {}
}
```
