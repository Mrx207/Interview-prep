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
