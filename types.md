# Use Flow

One of the most common bugs in React/Redux results from forgetting to wire up a handler to a dispatch, or an action to a reducer. Chasing these bugs is crazy-making. This is not what human minds are for. This is why we have computers. This kind of rinky-dink stuff should be handled by the tool.

Javascript by itself is too shapeless to allow our tools to catch this stort of type error, so we need to help it out. This is where a statically typed superset comes in. I prefer Flow, not because it's the best, but because it's the best that's also really easy to use.

Rely on static analysis to catch these bugs. No more "Why the freakin' heck is the action payload undefined?"

Use Flow in your IDE.

Let Flow write your PropTypes.

Is TypeScript better? Yes. So is Elm, Cotlin, and Elixir. But Flow gives you a huge boost, without leaving JSLand altogether.
