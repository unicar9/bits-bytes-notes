If you want to convert an array of say, number or string, into an array of objects, so these number or string will be used as key values, you can try below method:

```JavaScript

const fruitArray = ['apple', 'pear', 'banana', 'peach', 'waterlemon']

console.log(fruitArray.map(f => ({ fruitName: f, price: 10 }))) 

```

The result would be 

```JavaScript

[
    {fruitName: "apple", price: 10},
    {fruitName: "pear", price: 10},
    {fruitName: "banana", price: 10},
    {fruitName: "peach", price: 10},
    {fruitName: "waterlemon", price: 10}
]

```

Don't forget to use **parentheses** to wrap around the object, otherwise it won't work.