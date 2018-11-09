You can recreate a bullet list by adding below custom styles

Code:
```React

const styles = StyleSheet.create({
    listUnorderedItem: {
        paddingHorizontal: 16,
        flexDirection: 'row',
        justifyContent: 'flex-start',
        alignItems: 'flex-start'
    },
    listUnorderedItemIcon: {
        top: 10, // Adjust the number to reach the optimal effect
        fontSize: 25,
        lineHeight: 28
    },
    listItem: {
        fontSize: 18,
        lineHeight: 28
    }
})

<View style={styles.listUnorderedItem}>
    <Text style={styles.listUnorderedItemIcon}>{'\u2022'}</Text>
    <View style={styles.listItem}>{children}</View>
</View>

```