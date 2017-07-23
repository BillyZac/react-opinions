# Components vs Containers
A *component* should be unaware of the redux store. It takes props, and renders jsx. It's basically a template layer.

A *container* should contain no jsx. It is unaware of how the ui is displayed. It is connected to the store. It's one job is to map state and dispatch to props, and pass those props to components.
In fact, containers do not necessarily need to know about React at all. 

## Example: A save button

A button is just a button. You click on it and it does something. It could do anything. Of course, the thing that happens when the button is clicked should not be baked into the button itself.


The button is a component. JSX, styles, and that's it. Let's call it `<Button />`. We define the button's appearance here:
```
// components/Button.jsx
// import React, define Props, etc.

const Button = ({ label, handleClick }: Props) =>
   <button
     onClick={handleClick}
   >{label}</button>
```

The button's behavior is determined by a button container. We might have a button that saves our game when we click it. Let's call it `<SaveButton />`. We define the button's behavior here:
```
// containers/SaveButton.js
import { save } from '../actions/save'
import Button from '../components/Button'

const mapStateToProps = () => ({
  label: 'Save',
})

const mapDispatchToProps = dispatch => ({
  handleClick: () => { dispatch(save()) },
})

export default connect(mapStateToProps, mapDispatchToProps)(Button)
```

Then we can just use it wherever we need a save button. 
```
import SaveButton from '../containers/SaveButton'

const HomePage = () => (
  <div>
    <GameStuff />
    <SaveButton />
  </div>  
)
```

Note the neat separation of concerns. `Button.jsx` is responsible solely for displaying a button. `SaveButton.js` is responsible solely for defining the behavior of a button, but it has no notion of how the button is rendered. And `HomePage.jsx` knows only that it needs to put a Save button on the screen, and has no knowledge of how the button works, giving us a very readable, declarative way of describing our page. Which, I think, is how it should be.
