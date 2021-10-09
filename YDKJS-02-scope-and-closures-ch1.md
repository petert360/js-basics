# Chapter 1: What is Scope?

## [Compiler terminology](https://github.com/getify/You-Dont-Know-JS/blob/1st-ed/scope%20%26%20closures/ch1.md#compiler-speak)

### Look-up types

* LHS:  left-hand side of an assignment operator, meaning: "[who's the TARGET of the assignment][1]".  
LHS look-up can be phrased as a [CONTAINER look-up][2]
* RHS:  right-hand side of an assignment operator, meaning "[who's the SOURCE of the assignment][1]".  
RHS look-up can be phrased as a [VALUE look-up][2]

### Examples
```javascript
function foo(a) {
	console.log( a ); // 2
}

foo( 2 );
```
1. `foo( 2 );` delivers an RHS look-up to the value of `foo`. 
2. `foo( 2 );` also implies the `a = 2` assignment, which delivers an LHS look-up in order to assing `2` to the parameter `a`
3. `console.log(a)`  
   * RHS lookup is required for the value of `a`
   * `console.log(...)` needs a reference to execute, therfore an RHS look-up is required for the console object.
   * after the value of `a` is available by an RHS look-up, inside the log(...), it's first parameter (e.g. `arg1`) will get the value of `a` by an LHS look-up.



[1]: <https://github.com/getify/You-Dont-Know-JS/blob/1st-ed/scope%20%26%20closures/ch1.md#:~:text=Note%3A%20LHS%20and,the%20assignment%20(RHS)%22.>

[2]: <https://stackoverflow.com/questions/36383795/javascript-lhs-and-rhs-lookup#:~:text=LHS%20look-up,a%20value%20lookup> "LHS/RHS looh-up"
