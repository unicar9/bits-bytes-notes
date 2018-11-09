This is useful for a scenario where you want to display a Back to Top button on screen right when you scroll down to the bottom. So a setState function can be triggered inside a event that detects a scroll end. 

Notice that in React Native there are 2 different props can help us do this:

`onScrollEndDrag` and `onMomentumScrollEnd`, the difference is that the former one is called as soon as the user lets go of the ScrollView (lifts the finger from the screen), and the latter is called when the ScrollView stops sliding (it will normally continue to slide a little bit after the user has lifted the finger from the screen).

[source](https://stackoverflow.com/questions/41793549/detect-scroll-end-in-react-native-scrollview-snap-to-pag)

And then compare the value of between contentSize height and screen height plus offset height, see below:

Code:
```React

    <SectionList
        ref={(ref) => this.sectionListRef = ref}
        onScroll={Animated.event(
            [{ nativeEvent: {
                contentOffset: {
                    y: this.state.scrollY
                }
            }
            }])}
        onMomentumScrollEnd={(e) => {
            const ne = e.nativeEvent
            const h = ne.contentSize.height
            const offsetY = ne.contentOffset.y
            const wh = Dimensions.get('window').height

            if (offset + wh - h >= 0) {
                console.log('Scrolled to bottom!')
               // setState is triggered here
            }
        }}
    />

```
