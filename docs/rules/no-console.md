# Disallow Use of console (no-console)

In JavaScript that is designed to be executed in the browser, it's considered a best practice to avoid using methods on `console`. Such messages are considered to be for debugging purposes and therefore not suitable to ship to the client. In general, calls using `console` should be stripped before being pushed to production.

```js
console.log("Made it here.");
console.error("That shouldn't have happened.");
```


## Rule Details

This rule is aimed at eliminating unwanted `console` references from your JavaScript. As such, it warns whenever it sees `console` used as an identifier in code.

The following patterns are considered warnings:

```js
console.log("Hello world!");
console.error("Something bad happened.");
```

The following patterns are considered okay and do not cause warnings:

```js
// custom console
Console.log("Hello world!");
```

## When Not To Use It

If you're using Node.js, however, `console` is used to output information to the user and so is not strictly used for debugging purposes. If you are developing for Node.js then you most likely do not want this rule enabled.

## Further Reading

* [Use Uglify to automatically strip debug messages from your JavaScript](http://jstarrdewar.com/blog/2013/02/28/use-uglify-to-automatically-strip-debug-messages-from-your-javascript)

## Related Rules

* [no-alert](no-alert.md)
* [no-debugger](no-debugger.md)
