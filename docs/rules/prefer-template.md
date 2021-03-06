# Suggest using template literals instead of string concatenation. (prefer-template)

In ES2015 (ES6), we can use template literals instead of string concatenation.

```js
var str = "Hello, " + name + "!";
```

```js
var str = `Hello, ${name}!`;
```

## Rule Details

This rule is aimed to flag usage of `+` operators with strings.

The following patterns are considered warnings:

```js
var str = "Hello, " + name + "!";
```

The following patterns are not considered warnings:

```js
var str = "Hello World!";
```

```js
var str = `Hello, ${name}!`;
```

## When Not to Use It

This rule should not be used in ES3/5 environments.

In ES2015 (ES6) or later, if you don't want to be notified about string concatenation, you can safely disable this rule.
