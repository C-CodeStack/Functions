# JavaScript Functions 
Last time you learned about `loops`. Loops allow us to repeat a block of code. If you wanted to run the repeating loop again sometime later in the code then you would have to rewrite the loop in multiple places

```javascript
for (i = 0; i < 10; i++) { //first time writing the loop
  console.log("I am saying this 10 times")
}

console.log("Now I am done but I want to say it again")

for (i = 0; i < 10; i++) {//second time writing the same loop
  console.log("I am saying this 10 times")
}

console.log("and again")
//third time writing the same loop
//fourth time writing the same loop
//.....
```

This breaks a fundamental rule in coding `DRY` or `writing DRY code`. DRY stands for `Don't Repeat Yourself`. The code above would be considered `not DRY` as we repeat the exact same for loop many times. What if you repeated this for loop 100 times and then realized you really wanted this:

```javascript
for (i = 0; i < 9; i++) { //changed 10 to 9
  console.log("I am saying this 9 times")//changed 10 to 9
}
```

As your code is not DRY you would have to make that change in each of the 100 repeated for loops. If you miss just one change your code could be broken. As you can see more code creates complication. So keeping it consice and DRY is helpful.

To make this code DRY you need to use a function. A function repeats a block of code whenever you call it. So lets rewrite (`refactor`) your repeating code into a function. 

```javascript
//this is the old way function are defined
function oldWay() {
  for (i = 0; i < 10; i++) {
    console.log("I am saying this 10 times")
  }
}

//this is the new way functions are defined
const newWay = () => {//const means constant or a variable that cannot be re-assigned
  for (i = 0; i < 10; i++) {
    console.log("I am saying this 10 times")
  }
}
```

Both of these functions will work exactly the same. These lessons will always use the new way but be aware that you will see examples on the internet using the old way.

Now that we know our function lets refactor the remainder of your code to use that function

```javascript
const newWay = () => {//const means constant or a variable that cannot be re-assigned
  for (i = 0; i < 10; i++) {
    console.log("I am saying this 10 times")
  }
}

newWay()

console.log("Now I am done but I want to say it again")

newWay()

console.log("and again")
//third time writing the same loop
newWay()
//fourth time writing the same loop
newWay()
//.....
```

Each time you see newWay() it will log `I am saying this 10 times`. This code is DRY because it no longer repeates the for loop everywhere. Also, if we wanted to change those 10's to 9's we would only have to change it in one place and it would be fixed everywhere.

## Task 1
1. Declare a function called `areaRectangle` and assign it an anonomous function
2. Declare a variable `length` and assign it `2`
3. Declare a variable `width` and assign it `3`
4. log the `area` of this rectangle

Remember `area = length x width`

5. Call this function 3 times
#

Sometimes you want the function to log its results and sometimes you want it to pass its results to a variable. This is easily done with the `return statement`. When the `return` statement is ran it will pass back whatever is following it and it will terminate the function.

```javascript
const areaCircle = () => {
  let radius = 2
  return 3.14 * radius ** 2 // area = pi * r^2 
  // r^2 = r * r, r**2 = r * r
}

let area = areaCircle() //area = 12.56
```

## Task 2
1. Declare a function called `areaRectangle2` and assign it an anonomous function
2. Declare a variable `length` and assign it `2`
3. Declare a variable `width` and assign it `4`
4. return the `area` of this rectangle

Remember `area = length x width`

5. outside of the function, call the function and save its returned value in the variable `areaRect`
6. log areaRect
#

All of the functions thus far are static. That is, they do the exact same thing every time you call them. Sometimes this is exactly what you are looking for but sometimes you would like to do almost the same thing. For `areaCirlce` you would like it to calculate the area for different types of circles. This way you could ask for the area of a circle with radius 3,4,5,100,...,x. If you could accomplish this, it would no longer be necessary to memorize how to calculate the area of a circle. You can do this by giving the function `areaCircle` a `parameter`.

```javascript
const areaCircle = (radius) => {//parameter is radius
  return 3.14 * radius ** 2 //this is the same radius from the line above
}

console.log(areaCirlce(2))//->12.56
console.log(areaCirlce(3))//->28.26
console.log(areaCirlce(4))//->50.24

//we can have more than one parameter
const functionName = (param1, param2, param3,...) => {
  
}
```

An extra note about parameters. When we use it in defining the function, like the first and second lines above, then it is called a `parameter`. However, when we use it in areaCircle(2), areaCircle(3), areaCircle(4) radius is now holding data. When it is holding data it is called an `argument`

## Task 3
1. Declare a function called `areaRectangle3` and assign it an anonomous function
2. use `length, width` as parameter
3. return the `area` of this rectangle

Remember `area = length x width`

4. outside of the function, call the function with 2X3 as arguments
5. log the results
6. outside of the function, call the function with 3X4 as arguments
7. log the results
8. outside of the function, call the function with 4X5 as arguments
9. log the results
#

## Task 4
1. Declare a function called `areaSquare` and assign it an anonomous function
2. use `side` as parameter
3. return the `area` of this square

Remember `area = side ^ 2` or `side * side`

4. outside of the function, call the function with 3 as argument
5. log the results
6. Declare a function called `areaTri` and assign it an anonomous function
7. use `base and height` as parameters
8. return the `area` of this triangle

Remember `area = (base * height) / 2`

9. outside of the function, call the function with 2,3 as arguments
10. log the results
#

## Task 5a
1. Declare a function called `permRect` and assign it an anonomous function
2. use `length, width` as parameters
3. return the `perimeter` of this rectangle

Remember `perimeter = 2 * length + 2 * width`

4. outside of the function, call the function with 2,3 as arguments
5. log the results
#
## Task 5b
   
1. Declare a function called `permCircle` and assign it an anonomous function
2. use `radius` as parameter
3. return the `perimeter` of this circle

Remember `perimeter = 2 * 3.14 * radius`

4. outside of the function, call the function with 3 as argument
5. log the results
#
## Task 5c

1. Declare a function called `permSquare` and assign it an anonomous function
2. use `side` as parameters
3. return the `perimeter` of this square

Remember `perimeter = side * 4`

4. outside of the function, call the function with 3 as argument
5. log the results
#
## Task 5d

1. Declare a function called `permTri` and assign it an anonomous function
2. use `side` as parameter
3. return the `perimeter` of this triangle

Remember `perimeter = side * 3`

4. outside of the function, call the function with 3 as argument
5. log the results
#

## Task 6
1. Declare a function called `rectAll` and assign it an anonomous function
2. use `length, width` as parameters
3. log `Perimeter` (log the actual calculated perimeter)
4. log `Area` (log the actual calculated area)

Remember you already did all of these calculations. Do not cut and paste them because that will not be `DRY`. Find a better way.

5. outside of the function, call the function with 2,3 as arguments
