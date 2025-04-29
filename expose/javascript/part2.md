1.  Line 12 will print the value `3`. The variable `i` is declared using `var` in the `for` loop header (`var i = 0;`). Variables declared with `var` have function scope, not block scope. This means `i` is accessible throughout the entire `discountPrices` function, even outside the `for` loop. The loop iterates for `i` values 0, 1, and 2. The loop terminates when `i` becomes 3 (because the condition `i < 3` becomes false). Therefore, when `console.log(i)` is executed on line 12 after the loop has finished, it accesses the variable `i` from the function scope, which holds the value 3. The code does not cause an error.

2.  Line 13 will print the value `150`. The variable `discountedPrice` is declared using `var` inside the `for` loop (line 7). Like other variables declared with `var`, it has function scope, making it accessible outside the loop. Inside the loop, `discountedPrice` is reassigned in each iteration. Its final value after the last iteration (when `i` was 2) is `300 * (1 - 0.5)`, which equals 150. Since line 13 is executed after the loop finishes, `console.log(discountedPrice)` accesses this final value from the function scope and prints `150`. The code does not cause an error.

3.  Line 14 will print the value `150`. The variable `finalPrice` is declared using `var` at the beginning of the function (line 4), giving it function scope. Although it's reassigned within the `for` loop (line 8) in each iteration, it remains accessible outside the loop. Its value is updated in each iteration based on the calculated `discountedPrice`. The last update occurs when `i` is 2, setting `finalPrice` to 150. Since line 14 executes after the loop finishes, `console.log(finalPrice)` accesses this final value from the function scope and prints `150`. The code does not cause an error.

4.  The function will return the array `[50, 100, 150]`. The `for` loop iterates through the input `prices` array `[100, 200, 300]` with a discount of 0.5. In each iteration, it calculates the discounted price, rounds it to two decimal places storing it in `finalPrice`, and then pushes this `finalPrice` into the `discounted` array. After the loop completes, the `discounted` array holds the values `[50, 100, 150]`. The `return discounted;` statement on line 16 then explicitly returns this array as the result of the function call. The code does not cause an error.

5.  Line 12 will cause an error. The loop counter variable `i` is declared using `let` in the `for` loop header (`let i = 0;`). Unlike `var` which has function scope, `let` provides block scope. In the context of a `for` loop declaration, this means the scope of `i` is limited strictly to the loop itself (the block from lines 6 to 10). Once the loop finishes executing and the program control moves outside the loop block to line 12, the variable `i` no longer exists in the current scope. Therefore, attempting to access `i` with `console.log(i)` results in a `ReferenceError: i is not defined`.

6.  Line 13 will cause an error. The variable `discountedPrice` is declared using `let` *inside* the `for` loop block (line 7). `let` provides block scope, meaning `discountedPrice` only exists within the scope of a single iteration of the loop block (from line 7 to line 10). Once the loop finishes and execution moves outside the loop to line 13, the `discountedPrice` variable from the last iteration (or any iteration) is no longer in scope and therefore is not defined in the context of line 13. Attempting to access it results in a `ReferenceError: discountedPrice is not defined`.

7.  Line 14 will print the value `150`. The variable `finalPrice` is declared using `let` on line 4, *outside* the `for` loop block. This gives `finalPrice` function block scope (from line 2 to 17). Although it is reassigned within the loop on line 8, the variable itself exists and is accessible throughout the function. The loop updates its value in each iteration, with the final value being 150 after the iteration where `i` was 2. Since line 14 is within the scope where `finalPrice` was declared and executed after the loop finishes, `console.log(finalPrice)` successfully accesses the variable and prints its final assigned value, 150. The code does not cause an error.

8.  The function will return the array `[50, 100, 150]`. Although the variables `i` and `discountedPrice` were declared with `let`, limiting their scope to the loop block, this does not affect the calculation of `finalPrice` or the ability to push `finalPrice` into the `discounted` array in each iteration. The `discounted` array itself is declared with `let` at the function scope level (line 3) and is correctly populated within the loop. After the loop finishes, the `discounted` array contains `[50, 100, 150]`. The `return discounted;` statement on line 16 returns this populated array. The code executes without error and produces the same final returned array as the version using `var` (Question 4).

9.  Line 11 will cause an error. The loop counter variable `i` is declared using `let` in the `for` loop header (`let i = 0;` on line 6). As established previously, `let` provides block scope, and when used in a `for` loop declaration, the scope of `i` is strictly limited to the loop block (lines 6 to 9). Once the loop finishes and execution moves outside the loop to line 11, the variable `i` is no longer in scope and is therefore undefined. Attempting to access `i` with `console.log(i)` results in a `ReferenceError: i is not defined`. The use of `const` for `discounted`, `length`, and `discountedPrice` does not change the scope of `i`.

10. Line 12 will print the value `3`. The variable `length` is declared using `const` on line 4, *outside* the `for` loop block, and assigned the value of `prices.length`, which is 3. This declaration gives `length` function block scope (from line 2 to 15). Since `length` is declared in a scope that encloses line 12, and line 12 is executed after the loop finishes, `console.log(length)` successfully accesses the variable `length` and prints its constant value, 3. The code does not cause an error.

11. The function will return the array `[50, 100, 150]`. The code initializes a constant `discounted` array (line 3) and a constant `length` (line 4). The `for` loop (using `let i`) iterates correctly. Inside the loop, a block-scoped constant `discountedPrice` is calculated in each iteration (50, 100, 150 respectively for i=0, 1, 2). This calculated `discountedPrice` is then pushed into the `discounted` array (line 8). Using `const` for `discounted` is valid because its contents are being modified (via `.push`), not the variable assignment itself. Using `const` for `discountedPrice` inside the loop is also valid as a new constant is created per iteration block. After the loop completes, the `discounted` array holds `[50, 100, 150]`. The `return discounted;` statement on line 14 returns this array. The code does not cause an error. (Note: compared to Q8, the rounding step is removed, but for this specific input, the results are integers anyway).

12.
    a. `student.name`
    b. `student['Grad Year']`
    c. `student.greeting()`
    d. `student['Favorite Teacher'].name`
    e. `student.courseLoad[0]`

13. Arithmetic
    A. `'3' + 2` -> `'32'` (String concatenation occurs because one operand is a string. `2` is converted to `'2'`.)
    B. `'3' - 2` -> `1` (Subtraction attempts numeric conversion. `'3'` becomes `3`. `3 - 2 = 1`.)
    C. `3 + null` -> `3` (In arithmetic operations, `null` is converted to `0`. `3 + 0 = 3`.)
    D. `'3' + null` -> `'3null'` (String concatenation occurs. `null` is converted to the string `'null'`.)
    E. `true + 3` -> `4` (In arithmetic operations, `true` is converted to `1`. `1 + 3 = 4`.)
    F. `false + null` -> `0` (In arithmetic operations, `false` becomes `0` and `null` becomes `0`. `0 + 0 = 0`.)
    G. `'3' + undefined` -> `'3undefined'` (String concatenation occurs. `undefined` is converted to the string `'undefined'`.)
    H. `'3' - undefined` -> `NaN` (Subtraction attempts numeric conversion. `'3'` becomes `3`. `undefined` becomes `NaN`. `3 - NaN = NaN`.)

14. Comparison
    A. `'2' > 1` -> `true` (Comparison converts string '2' to number 2. `2 > 1` is true.)
    B. `'2' < '12'` -> `false` (String comparison is lexicographical. '2' comes after '1', so '2' is considered greater than '12'.)
    C. `2 == '2'` -> `true` (Loose equality `==` performs type coercion. String '2' is converted to number 2. `2 == 2` is true.)
    D. `2 === '2'` -> `false` (Strict equality `===` checks type and value. Number type is not equal to String type.)
    E. `true == 2` -> `false` (Loose equality `==` performs type coercion. `true` is converted to number 1. `1 == 2` is false.)
    F. `true === Boolean(2)` -> `true` (`Boolean(2)` evaluates to `true`. Strict equality `===` checks type and value. `true` (boolean) is strictly equal to `true` (boolean).)

15. Explain the difference between the == and === operators.
    The `==` (loose equality) operator compares two values for equality after attempting to convert them to a common type (type coercion). If the types are different, it tries to make them the same before checking if the values are equal.
    The `===` (strict equality) operator compares two values for equality without performing any type conversion. It checks if both the value and the data type are the same. If the types are different, it immediately returns `false`.
    It is generally recommended to use `===` over `==` to avoid unexpected behavior from implicit type coercion. For example, `2 == '2'` is true, but `2 === '2'` is false.


17. The result of calling `modifyArray([1,2,3], doSomething)` will be the array `[2, 4, 6]`.

   **Walkthrough:**
   1. The `modifyArray` function is called with `array = [1, 2, 3]` and `callback = doSomething` function.
   2. An empty array `newArr` is created: `[]`.
   3. The `for` loop starts, iterating from `i = 0` to `i = 2`.
   4. **Iteration 1 (i=0):**
      - `callback(array[0])` becomes `doSomething(1)`.
      - `doSomething(1)` returns `1 * 2 = 2`.
      - `newArr.push(2)` makes `newArr` become `[2]`.
   5. **Iteration 2 (i=1):**
      - `callback(array[1])` becomes `doSomething(2)`.
      - `doSomething(2)` returns `2 * 2 = 4`.
      - `newArr.push(4)` makes `newArr` become `[2, 4]`.
   6. **Iteration 3 (i=2):**
      - `callback(array[2])` becomes `doSomething(3)`.
      - `doSomething(3)` returns `3 * 2 = 6`.
      - `newArr.push(6)` makes `newArr` become `[2, 4, 6]`.
   7. The loop finishes.
   8. The function returns `newArr`, which is `[2, 4, 6]`.

   This happens because `modifyArray` iterates through each element of the input array and applies the `doSomething` callback function (which doubles the number) to each element, collecting the results in a new array.

19. The output of the code is:
   1
   4
   3
   2

   **Explanation:**
   1. `console.log(1)` executes immediately.
   2. `setTimeout` for `console.log(2)` is scheduled for 1000ms later.
   3. `setTimeout` for `console.log(3)` is scheduled for 0ms later (meaning it's placed in the event queue to run after the current synchronous code finishes).
   4. `console.log(4)` executes immediately.
   5. After the main function code finishes, the event loop picks up the task scheduled with 0ms delay, so `console.log(3)` runs.
   6. Approximately 1000ms after it was scheduled, the task for `console.log(2)` runs.