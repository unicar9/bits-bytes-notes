
in `React Native` We can use the [`numberOfLines`](https://facebook.github.io/react-native/docs/text.html#numberoflines "numberOfLines") props  on a **`Text`** component to limit the total number of lines. 

This will truncate the text with an ellipsis after computing the text layout, including line wrapping, such that the total number of lines does not exceed this number.

Before:
![alt text](./img/overhang.png "text too long")

After:
![alt text](./img/elipsis.png "text too long")


Code:
```javaScript
<Text numberOfLines={1}>long long long long text<Text>
```
Will produce:
```
long long long…
```
Before 


This prop is commonly used with `ellipsizeMode`.

Use the [`ellipsizeMode`](https://facebook.github.io/react-native/docs/text.html#ellipsizemode) props to move the ellipsis to the head or middle. `tail` is the default value.

Code:
```javaScript
<Text numberOfLines={1} ellipsizeMode='head'}>long long long long text<Text>
```
Will produce:
```
…long long text
```
