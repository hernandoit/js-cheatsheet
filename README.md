# `JavaScript cheat sheet`

`Table of Contents`

- [condtionals](#conditional-statements)
- [loops](#loops)
- [terms](#terms)
- [this](#this)
- [forEach](#foreach)
- [map](#map)
- [filter](#filter)
- [findIndex](#findindex)
- [find](#find)
- [some](#some)
- [every](#every)

## Conditional statements
### `'if...else'` 

> The if statement executes a statement if a specified condition is truthy. If the condition is falsy, another statement can be executed.

```js
if (condition) {
   statement1
} else {
   statement2
}
```
## Loops
### `'while'` 

> The while statement creates a loop that executes a specified statement as long as the test condition evaluates to true. The condition is evaluated before executing the statement.

```js
while (condition)
  statement
```

### `'for'`

> The for statement creates a loop that consists of three optional expressions, enclosed in parentheses and separated by semicolons, followed by a statement to be executed in the loop.

```js
for ([initialization]; [condition]; [final-expression])
   statement
```


# `Terms`
1. `callback function` - is a function we pass to another function as an argument
2. `predicate function` - the function returns either `true` or `false` (a boolean value)
3. `anonymous function` - a function that does not have a name (that is not stored in a variable)
4. `named function` - a function that has a name (that is stored in a variable)
5. `implicit return` - return the only expression without explicitly writing the word "return" (An implied return)
6. `Globally scoped` variables aren't declared inside of any code block, and are available anywhere in the program.
7. `Locally scoped` variables are only available inside of the code block they're declared within. A let i = 0 declaration inside of a for loop is a classic example– you won't be able to access that particular i variable outside of the for loop.


## `this`
## How to determine what `this` refers to:
1. In a function invoked with new, `this` will be the constructed object.
2. In a function invoked with `.call` or `.apply`, `this` will be the first argument passed to call or apply.
3. In a function created with `.bind,` `this` will be the first argument passed to `.bind`.
4. In a (non-fat arrow) function declared as a method on an object, `this` will be the object on which the method is declared.
5. If none of the above apply, `this` will be either the global object, or undefined depending on whether `'use strict'` is enabled.


# `forEach`
## Description
For each element in our array, call the provided function on that element.

### Example action

```js
const array1 = ['a', 'b', 'c'];

array1.forEach(element => console.log(element));
```

## Parameters

1. callbackFn - a function to run on each element in the array
a. element - the current element being looped over
b. index - (optional) the index of the element (i in a normal for-loop)
c. array - (optional) the array `forEach` was called upon

## Return value
undefined


# `map`
## Description
Returns a **new array** where each element has been changed from the original array in some way.

Note: The `map` function does not modify the original array.

```js
const developers = ['John', 'Nathan', 'Nick']
```

### Example action
To uppercase each element

```js
developer.toUpperCase()

const uppercaseDevelopers = developers.map(dev => dev.toUpperCase())
```

### Example Output
```js
['JOHN', 'NATHAN', 'NICK']
```

## Parameters
1. callbackFn - This function is called on each element in the array. The value that is returned is added to the new array.

## Return Value
Returns a new array, where each element is what was returned from the callback function.


# `filter` 
### `(find all)`
## Description
Returns a new array with the elements that return `true`, when passed to our callback function.

## Example
### Example Array
```js
const developers = ['John', 'Nathan', 'Nick']
```

### Example action
Filter for names that start with 'N'
```js
// check if the first letter is N
dev[0] === 'N'

const developersStartsN = developers.filter(dev => dev[0] === 'N')
```

### Example Output
```js
['Nathan', 'Nick']
```

### Parameters
1. callbackFn - This function is run on each element. Return a truthy value to keep the element in the newly filtered array. Otherwise return a falsy value.
a. The callback parameters are the same as `forEach` and `map`

### Return Value
A new array, with elements that returned true when passed to the function.

If no elements return true, it returns an empty array.

# `findIndex` 
### `(find index of the first element)`
## Description
Returns the index of the first element, that returns `true` 
when passed out callback function. Returns -1 if no element returns `true`.

## Example
### Example Array
```js
const developers = ['John', 'Nathan', 'Nick']
```

### Example action
Find the index of the first name that starts with 'N'
```js
// check if the first letter is N
dev[0] === 'N'

const index = developers.findIndex(dev => dev[0] === 'N')
```

### Example Output
```js
1 (because Nathan starts with N)
```

## Parameters
1. callbackFn - A function to run on each element. If the element returns true, then `findIndex` will return the `index` of that element.

## Return Value
The index of the first element that returns `true` when passed to our callback function. Otherwise `-1`

# `find` 
### `(find one)`
## Description
Return the first element that returns `true` when passed to our callback function.

Otherwise, return `undefined`.

## Example
### Example Array
```js
const developers = ['John', 'Nathan', 'Nick']
```

### Example action
Find the first name that starts with 'N'
```js
// check if the first letter is N
dev[0] === 'N'

const developerStartsN = developers.find(dev => dev[0] === 'N')
```

### Example Output
```js
'Nathan' // Because Nathan is the first element that starts with N
```

## Parameters
1. callbackFn - A function to run on each element. If the element returns true, then `find` will return that `element`.

## Return Value
The value of the first element that returns true when passed to our `callback`.

Otherwise returns `undefined`.

# `some`
## Description
The some method returns `true` if **any** element in our array, returns `true when passed to the callback function.

Otherwise, if every element returned `false`. Then `some` will return `false`.


## Example
### Example Array
```js
const developers = ['John', 'Nathan', 'Nick']
```

### Example action
Find out if any (some) name starts with 'N'
```js
// check if the first letter is N
dev[0] === 'N'

const hasNameStartsN = developers.some(dev => dev[0] === 'N')
```

### Example Output
```js
true // Because Nathan's name starts with an N
```

## Parameters
1. callbackFn - A function to run on each element. If any (some) element returns true, then `some` will return `true`.

## Return Value
`true` if any element returns a `truthy` value when passed to our callback function.

`false` if **every** element returned a `falsy` value

# `every`
## Description
The `every` method returns `true` if **every** element in our array, returns `true` when passed to the callback function.

If **any** element returns `false`, `every` returns false.

## Example
### Example Array
```js
const developers = ['John', 'Nathan', 'Nick']
```

### Example action
Find out if **every** name starts with 'N'
```js
// check if the first letter is N
dev[0] === 'N'

const everyNameStartsN = developers.every(dev => dev[0] === 'N')
```

### Example Output
```js
false // Because not every name starts with N. John does not start with 'N'
```

## Parameters
1. callbackFn - A function to run on each element. If `every` element returns `true`, then `every` will return `true`.

## Return Value
`true` if the callbuck function, returns `true` for every element.

Otherwise, returns `false`
