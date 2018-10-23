To create a horizontal divider in `React Native`, simply use `View` plus some styles.

Code:
```React
<View 
    style={{
        borderBottomColor: '#137cbd',
        borderBottomWidth: 2,
        width: 100, 
        height: 100,
        alignSelf: 'center'
    }} 
/>
```

`width` and `height` are used to define the divider's size, and if the parent component already has `justifyContent: 'center'` and `alignItems: 'center'` to horizontally and vertically center the child components, `alignSelf: 'center'` is sufficient to center the divider itself.
