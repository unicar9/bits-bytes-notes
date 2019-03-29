A common gotcha for creating a fade out element in CSS animation is that if you set initial opacity to 1 and delay the animation, the element will reappear when it ends.

So the solution should be:

```CSS
.some-element {
	opacity: 0;
	animation: fadeOut 5s ease;
}

@keyframes fadeOut {
	0% { opacity: .1; }
	50% { opacity: .1; }
	100% { opacity: 0; }
}
```