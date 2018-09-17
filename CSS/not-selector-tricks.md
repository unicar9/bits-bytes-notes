style issues are hard to locate, use `!important` with caution. If you are applying `!important` to certain attibutes on a selector but wanting to spare some elements, you can use `:not` pseudo class.

I am using `!important` on `a`'s `color` properties:
```CSS
a {
    color: inherit !important
}
```
But I would like this rule not applying to class names starting with `abc`, here is what I write:
```css
a:not([class^="abc"]) {
    color: inherit !important;
}
```

Some useful selectors: 
`x[attribute=value]` 
```css
a[href="codepen.io"] {
    color: #ffffff;
}
```

`x[attribute^=value]` 
```css
a[class^="awesome"] {
    color: #ffffff; /* selects all link whose class name starts with awesome */   
}
```
`x[attribute*=value]` 
```css
a[class*="awesome"] {
    color: #ffffff; /* selects all link whose class name contains awesome */   
}
```




