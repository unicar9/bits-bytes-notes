If you want to convert an object into an array of objects, you can try below method:

```JavaScript

const fruitObject = {
    apple: 2,
    pear: 5,
    banana: 6,
    peach: 9,
    waterlemon: 10
}

```

The expected result is

```JavaScript

[
    {label: "apple", price: 2},
    {label: "pear", price: 5},
    {label: "banana", price: 6},
    {label: "peach", price: 9},
    {label: "waterlemon", price: 10}
]

```

The method used can be

```JavaScript

Object.keys(fruitObject).map(key => ({
    label: key,
    price: fruitObject[key],
}));

```

Don't forget to use **parentheses** to wrap around the object, otherwise it won't work.
