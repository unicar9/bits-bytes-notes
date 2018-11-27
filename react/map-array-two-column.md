2 column layout can be easily achieved by flexbox if there are only finite 2 `div`s under one container div. However, in React mapping an array of values into corresponding DOM elements is a more common pattern, so if you want to put them into 2 column grid, you have to firstly split them into 2 even parts, each part represents a column, and they can be vertically stacked.

Code:
```React

const secondColumnStart = Math.ceil(this.props.items.length / 2)

return (
    <div className="row">
        <div className="column1">
            {this.props.items.slice(0, secondColumnStart).map(item => (<Item {...item} />))}
        </div>
        <div className="column2">
            {this.props.items.slice(secondColumnStart).map(item => (<Item {...item} />))}
        </div>
    </div>
)

```

source: [How to show results of a map in two or more columns using react](https://stackoverflow.com/questions/48848462/how-to-show-results-of-a-map-in-two-or-more-columns-using-react)