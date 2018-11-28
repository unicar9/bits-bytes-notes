Below code snippet is for listening for window resize event in React. This is usually for tracking window width and adjust component width according.

Code:
```React

class Example extends React.Component {
    constructor() {
        super()

        this.state = { 
            height: window.innerHeight, 
            width: window.innerWidth
        }

        this.updateDimensions = this.updateDimensions.bind(this)
    }

    componentDidMount() {
        window.addEventListener("resize", this.updateDimensions)
    }

    componentWillUnmount() {
        window.removeEventListener("resize", this.updateDimensions)
    }

    updateDimensions() {
        this.setState({
            height: window.innerHeight, 
            width: window.innerWidth
        })
    }

    render() {
        return (...)
    }

}

```


source: [React Example - Listening for window resize event](https://codepen.io/jagretz/pen/VWbwOQ?editors=0010)