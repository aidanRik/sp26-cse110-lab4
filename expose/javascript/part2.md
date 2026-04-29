**CSE 110 - Lab 4 Part 2**
1. ^^^ What will happen at line 12 and why? If the code causes an error, explain why. \
The console will log 3, the current value of `i`. This happens because `i`is declared using var within the for block, and because var is function scoped it can be accessed anywhere inside the function discountPrices. 3 is logged because the length of prices is 3 and when the for loop ends when it reaches `i < prices.length`.

2. ^^^ What will happen at line 13 and why? If the code causes an error, explain why. \
The console will log 150, the current value of `discountedPrice`. This happens because `discountedPrice` is last set equal to `prices[i] * (1 - discount)` where `i = 3` `prices[i] = 300` and `discount = 0.5`.

3. ^^^ What will happen at line 14 and why? If the code causes an error, explain why. \
The console will log 150, the current value of `finalPrice`. This happens because `finalPrice` is last set to equal to `Math.round(discountedPrice * 100) / 100` where `discountedPrice = 150` so there will be no rounding done to it.

4. ^^^ What will this function return? Give a brief explanation why. If the code causes an error, explain why. ^^^ \
This function will return `[50, 100, 150]`, but nothing will be logged in the console because `discounted` just gets returned directly.

5. ^^^ What will happen at line 12 and why?  If the code causes an error, explain why. ^^^ (assume this function is being called like the others: discountPrices([100, 200, 300], 0.5)). \
There will be a reference error in the console. This is because we are using `let i = 0` and `let` is block scoped which means that it can only be accessed within the brackets it is declared, and `console.log(i)` is outside of the for loop.

6. ^^^ What will happen at line 13 and why?  If the code causes an error, explain why. ^^^ \
There will be a reference error in the console. This is because we are using `let discountedPrice = prices[i] * (1 - discount)` and `let` is block scoped which means that it can only be accessed within the brackets it is declared, and `console.log(discountedPrice)` is outside of the for loop.

7. ^^^ What will happen at line 14 and why?  If the code causes an error, explain why. ^^^ \
The console will log 150. This is because `finalPrice` doesn't use a block scoped type and therefore `finalPrice` can be accessed outside of the for loop.

8. ^^^ What will this function return? Give a brief explanation. If the code causes an error, explain why. ^^^ \
This function will directly return `[50, 100, 150]` which is the final value of `discounted`, but there will be nothing logged in the console.

9. ^^^ What will happen at line 11 and why? If the code causes an error, explain why. \
There will be a reference error in the console. This is because we are using `let i = 0` and `let` is block scoped which means that it can only be accessed within the brackets it is declared, and `console.log(i)` is outside of the for loop.

10. ^^^ What will happen at line 12 and why? If the code causes an error, explain why. \
The console will log 3, the constant value of length. This happens because we use `    const length = prices.length` and using `const` means that it's value cannot be changed and there are 3 values within `discounted`.

11. ^^^ What will this function return? Give a brief explanation. If the code causes an error, explain why. ^^^ \
The function will return `[ 50, 100, 150 ]` and no errors. This is because we use `const discounted = [];` which allows us to mutate the contents inside of `discounted` using `.push(discountedPrice)` instead of trying to reassign the variable. Also, because we use `const discountedPrice` we are allowed to re-declare a new value for each iteration of the for loop and not get stuck with the same value for all iterations.

12. Given the above Object, write the notation for:  (These should be in your part2.md) \
A. Accessing the value of the name property in the student object \
`student.name` \
B. Accessing the value of the Grad Year property in the student object \
`student['Grad Year']` \
C. Calling the function for the greeting property in the student object \
`student.greeting()` \
D. Accessing the name property of the object in the Favorite Teacher property in student \
`student['Favorite Teacher'].name` \
E. Access index zero in the array of the courseLoad property of the student object \
`student.courseLoad[0]`

13. Arithmetic \
A. '3' + 2 \
`32` is returned because the integer `2` is mapped to its string representation when using `+` with at least one string . \
B. '3' - 2 \
`1` is returned because the string `'3'` is mapped to its integer representation. \
C. 3 + null \
`3` is returned because `null` doesn't change mapping when using `+` \
D. '3' + null \
`3null` is returned because `null` is mapped to its string representation when using `+` with at least one string \
E. true + 3 \
`4` is returned because `true` gets mapped to its integer representation, `1`, when using `+` \
F. false + null \
`0` is returned because `false` gets mapped to its integer representation, `0`, when using `+` and null doesn't change mapping when using `+` \
G. '3' + undefined \
`3undefined` is returned because undefined gets mapped to its string representation when using `+` with at least one string \
H. '3' - undefined \
`NaN` is returned because `3` gets mapped to its integer representation when using `-` and undefined gets mapped to nothing. When undefined is in any math operation, the operation will return `NaN`.

14. Comparison \ 
A. '2' > 1 \
`true` is returned because `2` gets mapped to its integer representation. When comparing two different types in JS, they both get converted to numbers. \
B. '2' < '12' \
`false` is returned because both strings don't get converted and then they are compared lexicographically, so they compare 1st characters which are `2` and the `1` in `12` and since 2 is greater then 1 it is false. \
C. 2 == '2' \
`true` is returned because `'2'` gets converted to an integer. `==` is comparing if the two are equal. \
D. 2 === '2' \
`false` is returned becasue `===` checks if the two are equal without any type conversion applied. \
E. true == 2 \
`false` is returned because when there are two different types they both get converted to integers. So `true` converts to `1` and is therefore not equal to `2`. \
F. true === Boolean(2) \
`true` is returned because `Boolean()` will convert any non-zero number to `true`, and then `===` checks for equality without any type conversions which aren't needed because we applied the conversion directly with `Boolean(2)`.

15. Explain the difference between the == and === operators. \
The `==` operator will check for loose equality, meaning it will apply type conversions before checking for eqaulity. Meanwhile `===` will check for strict equality, meaning both value and type must match and it will not apply any type conversions before checking for equality.

16. Answer in `part2-question16.js`

17. If the function above is called with the following parameters modifyArray([1,2,3], doSomething), what will be the result? Briefly walk through how you arrived at that result. (This should be in your part2.md). Here we are passing in a function as a parameter, however we can also return a function from another function just as easily, you're encouraged to play around with callbacks as they are used heavily in frontend JS development. \
`[2,4,6]` will be returned. If we walk through the function `modifyArray` we can see that there is a for loop that will iterate over each item in `array` and apply the `callback` function to each one of those items before adding them to `newArr`. We run `modifyArray` with these parameters `([1,2,3], doSomething)`, where the function `doSomething` takes a `num` and multiplies it by 2, which gives us the answer: `[2,4,6]`.

18. Answer in `part2-question18.js`

19. 











