# lets-compare-global-state-with-react-hooks

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

## Comparison Table

<table>

<tr>
<th></th>
<th>Context value</th>
<th>Using subscriptions</th>
<th>Optimization for rendering big object</th>
<th>Dependencies</th>
<th>Package size</th>
</tr>

<tr>
<th><a href="https://github.com/dai-shi/react-tracked">react-tracked</a></th>
<td>state-based object</t3>
<td>Yes *1</td>
<td>Proxy-based tracking</td>
<td>No</td>
<td><a href="https://bundlephobia.com/result?p=react-tracked@0.7.0">1.5kB</a></td>
</tr>

<tr>
<th><a href="https://github.com/diegohaz/constate">constate</a></th>
<td>state-based object</td>
<td>No</td>
<td>No (should use multiple contexts)</td>
<td>No</td>
<td><a href="https://bundlephobia.com/result?p=constate@1.2.0">329B</a></td>
</tr>

<tr>
<th><a href="https://github.com/jamiebuilds/unstated-next">unstated-next</a></th>
<td>state-based object</td>
<td>No</td>
<td>No (should use multiple contexts)</td>
<td>No</td>
<td><a href="https://bundlephobia.com/result?p=unstated-next@1.1.0">362B</a></td>
</tr>

<tr>
<th><a href="https://github.com/react-spring/zustand">zustand</a></th>
<td>N/A</td>
<td>Yes</td>
<td>Selector function</td>
<td>No</td>
<td><a href="https://bundlephobia.com/result?p=zustand@1.0.3">742B</a></td>
</tr>

<tr>
<th><a href="https://github.com/atlassian/react-sweet-state">react-sweet-state</a></th>
<td>state-based object</t3>
<td>Yes *3</td>
<td>Selector function</td>
<td>No</td>
<td><a href="https://bundlephobia.com/result?p=react-sweet-state@1.0.4">4.5kB</a></td>
</tr>

<tr>
<th><a href="https://github.com/storeon/storeon">storeon</a></th>
<td>store</td>
<td>Yes</td>
<td>state names</td>
<td>No</td>
<td><a href="https://bundlephobia.com/result?p=storeon@0.9.4">337B</a></td>
</tr>

<tr>
<th><a href="https://github.com/dai-shi/react-hooks-global-state">react-hooks-global-state</a></th>
<td>state object</td>
<td>No *2</td>
<td>state names</td>
<td>No</td>
<td><a href="https://bundlephobia.com/result?p=react-hooks-global-state@0.14.0">913B</a></td>
</tr>

<tr>
<th><a href="https://github.com/reduxjs/react-redux">react-redux (hooks)</a></th>
<td>store</td>
<td>Yes</td>
<td>Selector function</td>
<td>Redux</td>
<td><a href="https://bundlephobia.com/result?p=react-redux@7.1.0">5.6kB</a></td>
</tr>

<tr>
<th><a href="https://github.com/dai-shi/reactive-react-redux">reactive-react-redux</a></th>
<td>state-based object</t3>
<td>Yes *1</td>
<td>Proxy-based tracking</td>
<td>Redux</td>
<td><a href="https://bundlephobia.com/result?p=reactive-react-redux@4.2.0">1.4kB</a></td>
</tr>

<tr>
<th><a href="https://github.com/ctrlplusb/easy-peasy">easy-peasy</a></th>
<td>store</t3>
<td>Yes</td>
<td>Selector function</td>
<td>Redux, immer, and so on</td>
<td><a href="https://bundlephobia.com/result?p=easy-peasy@3.0.1">9.5kB</a></td>
</tr>

<tr>
<th><a href="https://github.com/mobxjs/mobx-react-lite">mobx-react-lite</a></th>
<td>mutable state object</t3>
<td>No *4</td>
<td>Proxy-based tracking</td>
<td>MobX</td>
<td><a href="https://bundlephobia.com/result?p=mobx-react-lite@1.4.1">1.7kB</a></td>
</tr>

<tr>
<th><a href="https://github.com/avkonst/hookstate">hookstate</a></th>
<td>N/A</t3>
<td>Yes</td>
<td>Proxy-based tracking</td>
<td>No</td>
<td><a href="https://bundlephobia.com/result?p=@hookstate/core@0.10.1">2.6kB</a></td>
</tr>

</table>

- *1 Stops context propagation by `calculateChangedBits=0`
- *2 Uses `observedBits`
- *3 Hack with readContext
- *4 Mutation trapped by Proxy triggers re-render

## Contribution

TODO
