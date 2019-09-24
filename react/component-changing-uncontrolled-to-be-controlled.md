Saw this warning in console:

> Warning: A component is changing an uncontrolled input of type text to be controlled. Input elements should not switch from uncontrolled to controlled (or vice versa). Decide between using a controlled or uncontrolled input element for the lifetime of the component.

**solution:**

```react
value={this.state.fields.name || ''}   // (undefined || '') = ''
```

reason: [stackoverflow question](https://stackoverflow.com/questions/47012169/a-component-is-changing-an-uncontrolled-input-of-type-text-to-be-controlled-erro/47012342)
