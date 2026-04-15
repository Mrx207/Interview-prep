# Interview-prep
Creating a guide that can help for prepping for interviews

// 11 April
## Closures — Apr 11 2026
A closure is when a function remembers variables from 
its outer scope even after that outer function has finished.

Example I wrote:
function counter() {
    let count = 0;
    return function() {
        count++;
        return count;
    }
}
const c = counter();
c() // 1
c() // 2 — count is remembered!

Why it matters in interviews: used in debounce, throttle, 
memoization, module pattern.

## Closures — Apr 15 2026

Definition: A function that remembers its lexical environment 
even after the outer function has finished.

All functions in JS are closures.

Lexical environment = the scope where the function was WRITTEN,
not where it was called.

Classic interview question — var vs let in setTimeout loop:
- var: one shared variable → prints 3 3 3
- let: fresh variable per iteration → prints 0 1 2
Fix: just change var to let. That's it.

IIFE = Immediately Invoked Function Expression
Old school fix before let existed.
(function(j) { ... })(i)

## Hoisting
- function declarations → fully hoisted, usable before declaration
- let/const function expressions → temporal dead zone, NOT hoisted
- Has NOTHING to do with closures

## this keyword

4 rules in order of priority:
1. new binding — this = new object
2. Explicit — call/apply/bind — this = whatever you pass
3. Implicit — obj.method() — this = obj
4. Default — just fn() — this = window or undefined(strict)

Arrow functions — NO own this, inherit from outer scope
Never use arrow functions as object methods if you need this

## call vs apply vs bind
- call(obj, arg1, arg2) → runs immediately, comma args
- apply(obj, [arg1, arg2]) → runs immediately, array args  
- bind(obj, arg1, arg2) → returns new function, runs later
Memory trick: Call=Comma, Apply=Array, Bind=later
