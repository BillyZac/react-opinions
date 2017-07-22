# Components vs Containers
A *component* should be unaware of the redux store. It takes props, and renders jsx. It's basically a template layer.

A *container* should contain no jsx. It is unaware of how the ui is displayed. It is connected to the store. It's one job is to map state and dispatch to props, and pass those props to components.

## Questions
Could we say that containers have no knowledge of React at all? No `ComponentDidMount`, no `extends Component`? Not sure, need to think about that.

What about components with state?
What about network requests?
Hm, I need to think about that. 

