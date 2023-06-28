# React Fragment tag
`<Fragment>' is a built-in component that allows you to group multiple elements without introducing an extra DOM element. 
It's a way to return multiple elements from a component's render method without wrapping them in a single parent element. <br>

You can also use the shorthand syntax for fragmnets `<> </>`



```js
import {Fragment} from 'react';

App() {
  return() (
    <Fragment>
      <div>Hello</div>
      <div>Hi</div>
    </Fragment>
 )

}
```
---
Using `<Fragment>` or the shorthand syntax allows you to group elements without introducing any extra DOM nodes. <br>
It's particularly useful wehn you don't want to affect the layout or add unnecessary styles to your components.



