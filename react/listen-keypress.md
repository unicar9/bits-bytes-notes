For <div> tag to pick up keyboard events, simply add `tabIndex = '0'` so it can focus or `tabIndex = '-1'` to prevent it from getting the dotted border when focused.

Also note that, the `e.keyCode` is always 0, but `e.charCode` has the correct value.

Code:
```React

<div tabIndex="0" onKeyPress={(e) => console.log(e.charCode)>
    this div can now have focus and recieve keyboard events
</div>

```


source: [How can I give keyboard focus to a DIV and attach keyboard event handlers to it?](https://stackoverflow.com/questions/148361/how-can-i-give-keyboard-focus-to-a-div-and-attach-keyboard-event-handlers-to-it)