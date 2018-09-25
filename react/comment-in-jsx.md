HTML comments inside of JSX won't work, you need to use JavaScript block comments and wrap them in curly brases:

Code:
```React
{/* A JSX comment */}
```

or
```React
{/* 
  Multi
  line
  comment
*/}
```

source: [How to comment in React JSX](https://wesbos.com/react-jsx-comments/)