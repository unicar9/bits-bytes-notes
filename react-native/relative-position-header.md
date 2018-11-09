With React Native column flex layout in nature, you can simply create a fixed header by giving it a `relative` position.

Code:
```React

const styles = StyleSheet.create({
    fixedHeader: {
        position: 'relative',
        top: 0,
        left: 0
    }
})
   
```