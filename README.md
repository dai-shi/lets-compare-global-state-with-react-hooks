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

## Comparison Table

<table>

<tr>
<th></th>
<th>Point 1</th>
<th>Point 2</th>
<th>Point 3</th>
<th>Point 4</th>
<th>Point 5</th>
<th>Point 6</th>
</tr>


<tr>
<th><a href="https://github.com/dai-shi/react-tracked">react-tracked</a></th>
<td>State-based object</td>
<td>Yes</td>
<td>Proxy-based tracking and selector function</td>
<td>No</td>
<td>Yes</td>
<td>Yes</td>
</tr>


<tr>
<th><a href="https://github.com/diegohaz/constate">constate</a></th>
<td>State-based object</td>
<td>No</td>
<td>No</td>
<td>No</td>
<td>Yes</td>
<td>Yes</td>
</tr>


<tr>
<th><a href="https://github.com/jamiebuilds/unstated-next">unstated-next</a></th>
<td>State-based object</td>
<td>No</td>
<td>No</td>
<td>No</td>
<td>Unknown (maybe yes)</td>
<td>Unknown (maybe yes)</td>
</tr>


<tr>
<th><a href="https://github.com/react-spring/zustand">zustand</a></th>
<td>No</td>
<td>Yes</td>
<td>Selector function</td>
<td>No</td>
<td>No</td>
<td>No</td>
</tr>


<tr>
<th><a href="https://github.com/atlassian/react-sweet-state">react-sweet-state</a></th>
<td>State-based object</td>
<td>Yes</td>
<td>Selector function</td>
<td>No</td>
<td>No</td>
<td>No</td>
</tr>


<tr>
<th><a href="https://github.com/storeon/storeon">storeon</a></th>
<td>Store</td>
<td>Yes</td>
<td>Shallow state properties</td>
<td>No</td>
<td>No</td>
<td>No</td>
</tr>


<tr>
<th><a href="https://github.com/dai-shi/react-hooks-global-state">react-hooks-global-state</a></th>
<td>State object</td>
<td>No</td>
<td>Shallow state properties</td>
<td>No</td>
<td>Yes</td>
<td>No</td>
</tr>


<tr>
<th><a href="https://github.com/reduxjs/react-redux">react-redux (hooks)</a></th>
<td>Store</td>
<td>Yes</td>
<td>Selector function</td>
<td>Redux</td>
<td>No</td>
<td>No</td>
</tr>


<tr>
<th><a href="https://github.com/dai-shi/reactive-react-redux">reactive-react-redux</a></th>
<td>State-based object</td>
<td>Yes</td>
<td>Proxy-based tracking and selector function</td>
<td>Redux</td>
<td>Yes</td>
<td>No</td>
</tr>


<tr>
<th><a href="https://github.com/ctrlplusb/easy-peasy">easy-peasy</a></th>
<td>Store</td>
<td>Yes</td>
<td>Selector function</td>
<td>Redux, immer and so on</td>
<td>Unknown (maybe no)</td>
<td>Unknown (maybe no)</td>
</tr>


<tr>
<th><a href="https://github.com/mobxjs/mobx-react-lite">mobx-react-lite</a></th>
<td>Mutable state object</td>
<td>No</td>
<td>Proxy-based tracking</td>
<td>MobX</td>
<td>No</td>
<td>No</td>
</tr>


<tr>
<th><a href="https://github.com/avkonst/hookstate">hookstate</a></th>
<td>No</td>
<td>Yes</td>
<td>Proxy-based tracking</td>
<td>No</td>
<td>Unknown</td>
<td>Unknown</td>
</tr>


</table>

## Contribution

TODO
