# React Opinions

## Motivation
Opinions are necessary. Without opinions, the team spends time debating small trivial matters. This would be fine, if we lived in a realm of engineering purity. But we don't. We live in the real world, and we are paid to solve real problems for real people. Time spent debating trivial matters is time not spent delivering features.

Okay, fine, but why not use an existing framework? That's what they're for, right? Angular, Loopback, Jumpsuit, MobX. They're all meant to abstract away the little details so that developers can focus on features. Yes, and that's great. But I personally like to dig into the details, and know exactly how things work, and understand why such and such a decision was made.  

quick-start-boilerplate that often ends up being more confusing than helpful, 

## Components vs Containers
A *component* should be unaware of the redux store. It takes props, and renders jsx. It's basically a template layer.

A *container* should contain no jsx. It is unaware of how the ui is displayed. It is connected to the store. It's one job is to map state and dispatch to props, and pass those props to components.

Could we say that containers have no knowledge of React at all? No `ComponentDidMount`, no `extends Component`? Not sure, need to think about that.

What about components with state?
What about network requests?
Hm, I need to think about that. 

## Granularity
Nothing is too small to be a component. If it is a thing on the screen, it deserves to have it's own file and it's own name.

We should think of it like this: Anything may be complex. We just don't know. It may look small, or seem simple, and maybe it is, for now. But we don't know what kind of magic goes into that small, simple thing. And we don't care, as long as it does it's job. 

It may be simple now, but we should have a structure in place to allow for growth. The naive solution and the sophisticated solution should live within the same structure. By the same rules. The structure of the codebase is clear and readable, no matter the level of sophistication. As the codebase matures, it maintains its fundamental structure. It simply fills it in.

## What is Redux, actually?
more than just a library, but instead it’s own flux-like paradigm of reasoning about application state.

What is the difference between a framework and a library?

React is the best user-interface creation tool in existence, and Redux is an awesome, no funny-business state-management library 

