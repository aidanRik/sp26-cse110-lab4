**CSE 110 - Lab 4 Part 1**

1. What is printed by line 9? If the code returns an error, explain why. \
values added: 20

2. What is printed by line 13? If the code returns an error, explain why. \
final result: 20

3. Why should you not use var? Explain why. \ 
We should not use var because it uses function scope, which means no matter what line it is defined on it can be accessed anywhere inside that function. This can lead to confusing naming conflicts and misusing the variable in the wrong places.

4. What is printed by line 9? If the code returns an error, explain why. ^^^^^ \
values added: 20

5. What is printed by line 13? If the code returns an error, explain why. \
console.log('final result: ', result);
ReferenceError: result is not defined
This error is returned because we are using let instead of var, and let is different because it uses block scope. This means that result only exists within the brackets that it is defined in, therefore the if block that only has the first console log, which is why the second console log returns an undefined error.

6. What is printed by line 9? If the code returns an error, explain why. ^^^^^ \
There is an error before line 9 is able to run. This is specifically a type error which happens because we are using const for declaring result, and then on the next line we are trying to reassign the value of result which isn't allowed for the type const.

7. What is printed by line 13? If the code returns an error, explain why. \
There is an error before line 13 is able to run. This happens because of the same reason as before, there is a type error on `const result = 0`. Because we use const to define the result variable, we aren't allowed to reassign its value on the next line with `result = num1 + num2`






