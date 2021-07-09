### Control Flow 

## ifStatement

```js
const name = 'Mike' // Change me to a special name!
console.log(name)
// Write a program that asks a user what their name is
if (name === 'Rachel') {
  // If their name is Rachel, print 'Hi, Rachel!' to the console.
  console.log('Hi, Rachel!')
} else if (name === 'Mike') {
  // If their name is Mike, print 'Hi Mike!' to the console.
  console.log('Hi, Mike!')
} else if (name === 'Nikki') {
  // If their name is Nikki, print 'Hi, Nikki!' to the console.
  console.log('Hi, Nikki!')
} else {
  // If their name is not one of those three names, print 'Hi, stranger!' to the console.
  console.log('Hi, stranger.')
}
```

## whileLoop

```js
let count = 1
while (count < 5) {
  console.log('Inside of the loop, count is ' + count)
  count++
}
console.log('Outside of the loop, count is ' + count)
```

## forLoop

```js
for (let i = 0; i < 10; i++) {
  console.log(i)
}
let i = 0
while (i < 10) {
  console.log(i)
  i++
}
for (let i = 0; i < 10; i++) {
  if (i === 5) {
    console.log('Five!!')
  } else {
    console.log('Nah!!')
  }
}
```