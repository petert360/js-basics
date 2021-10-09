Unfulfilled RHS references result in `ReferenceError`s being thrown. Unfulfilled LHS references result in an automatic, implicitly-created global of that name (if not in "Strict Mode" [^note-strictmode]), or a `ReferenceError` (if in "Strict Mode" [^note-strictmode]).

### Quiz Answers

```js
function foo(a) {
	var b = a;
	return a + b;
}

var c = foo( 2 );
```

```js
function foo(a) {
	var b = a;
	return a + b;
}

var c = foo( 2 );
```

```js
function foo(a) {
	var b = a;
	return a + b;
}

var c = foo( 2 );
```
```js
function foo(a) {
	var b = a;
	return a + b;
}

var c = foo( 2 );
```

1. Identify all the LHS look-ups (there are 3!).

	**`c = ..`, `a = 2` (implicit param assignment) and `b = ..`**

2. Identify all the RHS look-ups (there are 4!).

    **`foo(2..`, `= a;`, `a + ..` and `.. + b`**


[^note-strictmode]: MDN: [Strict Mode](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions_and_function_scope/Strict_mode)


[^link-SO]: Stack Overflow - [JavaScript LHS and RHS Lookup](https://stackoverflow.com/questions/36383795/javascript-lhs-and-rhs-lookup#:~:text=LHS%20look-up,a%20value%20lookup)  


[^quote-YDKJS]: Kyle Simpson: [YDKJS - Scope & Closures - Ch1 - Errors](https://github.com/getify/You-Dont-Know-JS/blob/1st-ed/scope%20%26%20closures/ch1.md#:~:text=Because%20these%20two%20types%20of%20look-ups%20behave%20differently%20in%20the%20circumstance%20where%20the%20variable%20has%20not%20yet%20been%20declared%20(is%20not%20found%20in%20any%20consulted%20Scope).)
