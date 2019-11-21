# Let's compare global state with React Hooks

Comparing global state libraries with React Hooks

## Motivation

I have been developing several libraries for global state with React Hooks.
While developing them, I was interested in comparing with existing libraries.
It turns out there are various points to compare,
showing characteristics of such libraries.

I started creating a comparison table in
[the issue](https://github.com/dai-shi/react-tracked/issues/1).
As the table becomes bigger, let's create a separate repo
so that library authors can contribute improving the comparison.

## Comparison points

1. Does it use React Context? What is context value?
2. Does it use subscription for state propagation?
3. Does it have render optimization? What is the technique?
4. Does it have dependencies? What are they?
5. Does it avoid tearing in concurrent mode?
6. Does it support state branching in concurrent mode?

### Notes

Render optimization means avoiding unnecessary re-renders.
If a state object `{ a: 1, b: 2 }` and a component uses `a`,
it won't re-render if only `b` is changed.

For "tearing" and "state branching", refer
<https://github.com/dai-shi/will-this-react-global-state-work-in-concurrent-mode>.
These are not necessarily problems depending on requirements.

### TODO

- Bundle size
- js-framework-benchmark

## Libraries

### React Tracked

[GitHub](https://github.com/dai-shi/react-tracked)

1. Does it use React Context? What is context value?

Yes. State-based object.

2. Does it use subscription for state propagation?

Yes.

3. Does it have render optimization? What is the technique?

Yes. Both Proxy-based tracking and selector function.

4. Does it have dependencies? What are they?

No.

5. Does it avoid tearing in concurrent mode?

Yes.

6. Does it support state branching in concurrent mode?

Yes.

### Constate

[GitHub](https://github.com/diegohaz/constate)

1. Does it use React Context? What is context value?

Yes. State-based object.

2. Does it use subscription for state propagation?

No.

3. Does it have render optimization? What is the technique?

No.

4. Does it have dependencies? What are they?

No.

5. Does it avoid tearing in concurrent mode?

Yes.

6. Does it support state branching in concurrent mode?

Yes.

### Unstated Next

[GitHub](https://github.com/jamiebuilds/unstated-next)

1. Does it use React Context? What is context value?

Yes. State-baesd object.

2. Does it use subscription for state propagation?

No.

3. Does it have render optimization? What is the technique?

No.

4. Does it have dependencies? What are they?

No.

5. Does it avoid tearing in concurrent mode?

Unknown. Maybe yes.

6. Does it support state branching in concurrent mode?

Unknown. Maybe yes.

### Zustand

[GitHub](https://github.com/react-spring/zustand)

1. Does it use React Context? What is context value?

No.

2. Does it use subscription for state propagation?

Yes.

3. Does it have render optimization? What is the technique?

Yes. Selector function.

4. Does it have dependencies? What are they?

No.

5. Does it avoid tearing in concurrent mode?

No.

6. Does it support state branching in concurrent mode?

No.

### React Sweet State

[GitHub](https://github.com/atlassian/react-sweet-state)

1. Does it use React Context? What is context value?

Yes. State-based object.

2. Does it use subscription for state propagation?

Yes.

3. Does it have render optimization? What is the technique?

Yes. Selector function.

4. Does it have dependencies? What are they?

No.

5. Does it avoid tearing in concurrent mode?

No.

6. Does it support state branching in concurrent mode?

No.

### Storeon

[GitHub](https://github.com/storeon/storeon)

1. Does it use React Context? What is context value?

Yes. Store.

2. Does it use subscription for state propagation?

Yes.

3. Does it have render optimization? What is the technique?

Yes. Shallow state properties.

4. Does it have dependencies? What are they?

No.

5. Does it avoid tearing in concurrent mode?

No.

6. Does it support state branching in concurrent mode?

No.

### React Hooks Global State

[GitHub](https://github.com/dai-shi/react-hooks-global-state)

1. Does it use React Context? What is context value?

Yes. State object.

2. Does it use subscription for state propagation?

No.

3. Does it have render optimization? What is the technique?

Yes. Shallow state properties.

4. Does it have dependencies? What are they?

No.

5. Does it avoid tearing in concurrent mode?

Yes.

6. Does it support state branching in concurrent mode?

No.

## React Redux (Hooks)

[GitHub](https://github.com/reduxjs/react-redux)

1. Does it use React Context? What is context value?

Yes. Store.

2. Does it use subscription for state propagation?

Yes.

3. Does it have render optimization? What is the technique?

Yes. Selector function.

4. Does it have dependencies? What are they?

Yes. Redux.

5. Does it avoid tearing in concurrent mode?

No.

6. Does it support state branching in concurrent mode?

No.

### Reactive React Redux

[GitHub](https://github.com/dai-shi/reactive-react-redux)

1. Does it use React Context? What is context value?

Yes. State-based object.

2. Does it use subscription for state propagation?

Yes.

3. Does it have render optimization? What is the technique?

Yes. Both Proxy-based tracking and selector function.

4. Does it have dependencies? What are they?

Yes. Redux.

5. Does it avoid tearing in concurrent mode?

Yes.

6. Does it support state branching in concurrent mode?

No.

## Easy Peasy

[GitHub](https://github.com/ctrlplusb/easy-peasy)

1. Does it use React Context? What is context value?

Yes. Store.

2. Does it use subscription for state propagation?

Yes.

3. Does it have render optimization? What is the technique?

Yes. Selector function.

4. Does it have dependencies? What are they?

Yes. Redux, immer, and so on.

5. Does it avoid tearing in concurrent mode?

Unknown. Maybe no.

6. Does it support state branching in concurrent mode?

Unknown. Maybe no.

### MobX React Lite

[GitHub](https://github.com/mobxjs/mobx-react-lite)

1. Does it use React Context? What is context value?

Yes. Mutable state object.

2. Does it use subscription for state propagation?

No.

3. Does it have render optimization? What is the technique?

Yes. Proxy-based tracking.

4. Does it have dependencies? What are they?

Yes. MobX.

5. Does it avoid tearing in concurrent mode?

No.

6. Does it support state branching in concurrent mode?

No.

### Hookstate

[GitHub](https://github.com/avkonst/hookstate)

1. Does it use React Context? What is context value?

No.

2. Does it use subscription for state propagation?

Yes.

3. Does it have render optimization? What is the technique?

Yes. Proxy-based tracking.

4. Does it have dependencies? What are they?

No.

5. Does it avoid tearing in concurrent mode?

Unknown.

6. Does it support state branching in concurrent mode?

Unknown.

## Contribution

TODO
