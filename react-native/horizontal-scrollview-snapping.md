Add the following props in your ScrollView component when you want to create a snapping to center effect

Code:
```React
<ScrollView 
    horizontal= {true}
    decelerationRate={0}
    snapToInterval={200} //your element width
    snapToAlignment={"center"}
/>
```

source: [Horizontal scrollview snapping react native](https://stackoverflow.com/questions/39849648/horizontal-scrollview-snapping-react-native)