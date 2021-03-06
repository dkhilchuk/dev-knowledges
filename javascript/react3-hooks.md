## React 3 (Hooks)

- `useState` is hook that is analogue to `setState`, but it should be created for each data item.
`useEffect` is an analogue to componentUpdate hooks; It sets the document title after React updates the DOM.

```jsx

import React, { useState, useEffect } from 'react';

function Example() {
  const [count, setCount] = useState(0);

  // Similar to componentDidMount and componentDidUpdate:
  useEffect(() => {
    // Update the document title using the browser API
    document.title = `You clicked ${count} times`;
  });

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```

- You should return function from `useEffect` that will be called in the same moment as `componentWillUnmount` in class component. Next is an example with a subscribe/uncubscribe.

```jsx
useEffect(() => {
    ChatAPI.subscribeToFriendStatus(props.friend.id, handleStatusChange);

    return () => {
      ChatAPI.unsubscribeFromFriendStatus(props.friend.id, handleStatusChange);
    };
  });
```
