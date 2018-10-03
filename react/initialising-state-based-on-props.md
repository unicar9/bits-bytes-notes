Sometimes if you want to pass a part of parent component state to child component via props, and also use local state in child component to change this prop value. Which means, your local state needs to initialised by the parent prop value, however, if you just initialise the state value in the constructor, and when the parent prop value changes, it cannot be reflected in the local state.

Code:

```React
// in child component
class ChildComponent extends Component {
    constructor(){
        super(props);
        this.state = { bookings: this.props.bookings };
    }
    
    render() {
        { bookings } = this.state
        return (
            <div>I made {bookings} bookings!</div>
        )
     }
}

// In parent component
// Assuming this.state.bookings = 3
// The first time it will render correctly "I have 3 bookings!" 
<ChildComponent bookings = {this.state.bookings} />
// Now parent state "bookings" changed to 5
// This time child component will again render "I have 3 bookings!"
<ChildComponent bookings = {this.state.bookings} /> 

```

Why? **Because the constructor of the component is executed only once.**

Solution: `componentWillReceiveProps`
```React

class ChildComponent extends Component {
    constructor(){ ... }
    componentWillReceiveProps(nextProps) {
        if(nextProps.bookings !== this.props.bookings){
            this.setState({bookings: nextProps.bookings});
        }
    }
    render(){...}
}

```

React recommended approach: [Lifting State Up](https://reactjs.org/docs/lifting-state-up.html)

source: [Common pitfall in initialising state based on props in React JS](https://hackernoon.com/common-pitfall-in-initialising-state-based-on-props-in-react-js-d56795a944aa)