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
