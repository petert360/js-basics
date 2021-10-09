# Chapter 1: What is Scope?

## [Compiler terminology](https://github.com/getify/You-Dont-Know-JS/blob/1st-ed/scope%20%26%20closures/ch1.md#compiler-speak)

### Look-up types

* LHS:  left-hand side of an assignment operator, meaning: "who's the TARGET of the assignment" [^note-ydkjs].  
LHS look-up can be phrased as a CONTAINER look-up [^note-so]
* RHS:  right-hand side of an assignment operator, meaning "who's the SOURCE of the assignment" [^note-jdkjs].  
RHS look-up can be phrased as a VALUE look-up [^note-so]

### Example #1
```javascript
function foo(a) {
	console.log( a ); // 2
}

foo( 2 );
```
1. `foo( 2 );` delivers an RHS look-up to the value of `foo`. 
2. `foo( 2 );` also implies the `a = 2` assignment, which delivers an LHS look-up in order to assing `2` to the parameter `a`
3. `console.log(a)`  
   * RHS look-up is required for the value of `a`
   * `console.log(...)` needs a reference to execute, therfore an RHS look-up is required for the console object.
   * after the value of `a` is available by an RHS look-up, inside the log(...), it's first parameter (e.g. `arg1`) will get the value of `a` by an LHS look-up.

### Example #2
```javascript
function foo(a) {
	var b = a;
	return a + b;
}

var c = foo( 2 );
```
1. `var c = foo( 2 )`;  
    * RHS look-up for the value of `foo`
    * LHS look-up is performed th assing value `2` to target `a`
    * LHS look-up for assinging a value to the container called `c`
2. `var b = a;`  
    * RHS look-up for value `a`
    * LHS look-up for assinging value `a` to target `b`
3. `return a + b;`
    * 2 RHS look-ups for assigning values to targets `a` and `b`

## Errors
"_...these two types of look-ups behave differently in the circumstance where the variable has not yet been declared..._" [^quote-ydkjs]

* RHS look-up failure results in a `ReferenceError`
* LHS look-up failure results in a `ReferenceError`


[^note-strictmode]: Kyle Simpson: [YDKJS - Scope & Closures - Ch1 - Compiler speak](https://github.com/getify/You-Dont-Know-JS/blob/1st-ed/scope%20%26%20closures/ch1.md#:~:text=Note%3A%20LHS%20and,the%20assignment%20(RHS)%22.)

[^note-so]: Stack Overflow - [JavaScript LHS and RHS Lookup](https://stackoverflow.com/questions/36383795/javascript-lhs-and-rhs-lookup#:~:text=LHS%20look-up,a%20value%20lookup)  

[^quote-ydkjs]: Kyle Simpson: [YDKJS - Scope & Closures - Ch1 - Errors](https://github.com/getify/You-Dont-Know-JS/blob/1st-ed/scope%20%26%20closures/ch1.md#:~:text=Because%20these%20two%20types%20of%20look-ups%20behave%20differently%20in%20the%20circumstance%20where%20the%20variable%20has%20not%20yet%20been%20declared%20(is%20not%20found%20in%20any%20consulted%20Scope).)
