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
5. What's the level of compatibility with concurrent rendering?
6. Bundle size (Minified + Gzipped)

### Notes

Render optimization means avoiding unnecessary re-renders.
If a state object is `{ a: 1, b: 2 }` and a component only uses `a`,
it won't re-render if only `b` is changed.

For "tearing" and "state branching", refer
<https://github.com/dai-shi/will-this-react-global-state-work-in-concurrent-mode>.
These are not necessarily problems depending on requirements.

## Comparison Table

<table>

<tr>
<th></th>
<th>1</th>
<th>2</th>
<th>3</th>
<th>4</th>
<th>5</th>
<th>6</th>
</tr>


<tr>
<th><a href="https://github.com/dai-shi/react-tracked">react-tracked</a></th>
<td>State-based object</td>
<td>Yes</td>
<td>Proxy-based tracking and selector function</td>
<td>use-context-selector, proxy-compare</td>
<td>Level 3</td>
<td><a href="https://bundlephobia.com/package/react-tracked@1.7.5">1.9kB</a></td>
</tr>


<tr>
<th><a href="https://github.com/diegohaz/constate">constate</a></th>
<td>State-based object</td>
<td>No</td>
<td>Multiple contexts</td>
<td>No</td>
<td>Level 3</td>
<td><a href="https://bundlephobia.com/package/constate@3.3.0">508B<a/></td>
</tr>


<tr>
<th><a href="https://github.com/jamiebuilds/unstated-next">unstated-next</a></th>
<td>State-based object</td>
<td>No</td>
<td>No</td>
<td>No</td>
<td>Unknown</td>
<td><a href="https://bundlephobia.com/package/unstated-next@1.1.0">362B</a></td>
</tr>


<tr>
<th><a href="https://github.com/pmndrs/zustand">zustand</a></th>
<td>No</td>
<td>Yes</td>
<td>Selector function</td>
<td>No</td>
<td>Level 2</td>
<td><a href="https://bundlephobia.com/package/zustand@3.6.8">954B</a></td>
</tr>


<tr>
<th><a href="https://github.com/atlassian/react-sweet-state">react-sweet-state</a></th>
<td>State-based object</td>
<td>Yes</td>
<td>Selector function</td>
<td>No</td>
<td>Unknown</td>
<td><a href="https://bundlephobia.com/package/react-sweet-state@2.5.2">3.6kB</a></td>
</tr>


<tr>
<th><a href="https://github.com/storeon/storeon">storeon</a></th>
<td>Store</td>
<td>Yes</td>
<td>Shallow state properties</td>
<td>No</td>
<td>Unknown</td>
<td><a href="https://bundlephobia.com/package/storeon@3.1.4">370B</a></td>
</tr>


<tr>
<th><a href="https://github.com/dai-shi/react-hooks-global-state">react-hooks-global-state</a></th>
<td>No</td>
<td>Yes</td>
<td>Shallow state properties</td>
<td>No</td>
<td>Level 1</td>
<td><a href="https://bundlephobia.com/package/react-hooks-global-state@1.0.2">1.1kB</a></td>
</tr>


<tr>
<th><a href="https://github.com/reduxjs/react-redux">react-redux (hooks)</a></th>
<td>Store</td>
<td>Yes</td>
<td>Selector function</td>
<td>Redux</td>
<td>Level 2</td>
<td><a href="https://bundlephobia.com/package/react-redux@7.2.6">5.4kB</a></td>
</tr>


<tr>
<th><a href="https://github.com/ctrlplusb/easy-peasy">easy-peasy</a></th>
<td>Store</td>
<td>Yes</td>
<td>Selector function</td>
<td>Redux, immer and so on</td>
<td>Unknown</td>
<td><a href="https://bundlephobia.com/package/easy-peasy@5.0.4">9.6kB</a></td>
</tr>


<tr>
<th><a href="https://github.com/mobxjs/mobx-react-lite">mobx-react-lite</a></th>
<td>Mutable state object</td>
<td>No</td>
<td>Proxy-based tracking</td>
<td>MobX</td>
<td>Unknown</td>
<td><a href="https://bundlephobia.com/package/mobx-react-lite@3.2.2">2kB</a></td>
</tr>


<tr>
<th><a href="https://github.com/avkonst/hookstate">hookstate</a></th>
<td>No</td>
<td>Yes</td>
<td>Proxy-based tracking</td>
<td>No</td>
<td>Unknown</td>
<td><a href="https://bundlephobia.com/package/@hookstate/core@3.0.13">4.5kB</a></td>
</tr>


<tr>
<th><a href="https://github.com/facebookexperimental/Recoil">recoil</a></th>
<td>Probably rich state-based object</td>
<td>Yes with atom abstraction</td>
<td>atoms (incl. selectors)</td>
<td>No</td>
<td>Level 2</td>
<td><a href="https://bundlephobia.com/package/recoil@0.5.2">21.1kB</a></td>
</tr>


<tr>
<th><a href="https://github.com/RisingStack/react-easy-state">react-easy-state</a>(Note: This library does not provide Hooks API)</th>
<td>No</td>
<td>Yes with observer</td>
<td>observer</td>
<td>@nx-js/observer-util</td>
<td>Unknown</td>
<td><a href="https://bundlephobia.com/package/react-easy-state@6.1.3">2.9kB</a></td>
</tr>


<tr>
<th><a href="https://github.com/oleggrishechkin/react-tagged-state">react-tagged-state</a></th>
<td>No</td>
<td>Yes</td>
<td>Selector function with deps tracking</td>
<td>No</td>
<td>Unknown</td>
<td><a href="https://bundlephobia.com/package/react-tagged-state@1.0.6">804B</a></td>
</tr>


<tr>
<th><a href="https://github.com/agile-ts/agile">agile-ts</a></th>
<td>No</td>
<td>Yes</td>
<td>Runtime combining multiple rerender triggers</td>
<td>No</td>
<td>Unknown</td>
<td><a href="https://bundlephobia.com/package/@agile-ts/core@0.2.7">12.7kB<a></td>
</tr>


<tr>
<th><a href="https://github.com/pmndrs/jotai">jotai</a></th>
<td>Store</td>
<td>Yes, atom-based subscription</td>
<td>atoms</td>
<td>No</td>
<td>Level 1 / (Level 3)</td>
<td><a href="https://bundlephobia.com/package/jotai@1.4.9">2.6kB</a></td>
</tr>


<tr>
<th><a href="https://github.com/pmndrs/valtio">valtio</a></th>
<td>No</td>
<td>Yes</td>
<td>Proxy-based tracking</td>
<td>proxy-compare</td>
<td>Level 2</td>
<td><a href="https://bundlephobia.com/package/valtio@1.2.7">2.5kB</a></td>
</tr>

</table>

## Contribution

If you have questions, suggestions or corrections, please file an issue.

If you have a new library to add, please file a pull request. Please add a new row at the end of the table.
