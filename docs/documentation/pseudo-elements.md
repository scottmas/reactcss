---
id: pseudo-elements
title: Pseudo Elements
---

When looping through components, spread the `loop` method provided by ReactCSS and call it with the iterator to pass down list-specific props, like: `first-child` `last-child` `even` `odd` `nth-child-*`

```
import React from 'react'
import reactCSS, { loop } from 'reactcss'

const List = () => {
  return (
    <div style={ styles.list }>
      { this.props.items((item, i) => {
        return <ListItem { ...item } { ...loop(i) } />
      }) }
    </div>
  )
}

```

Use the props returned by the `loopable` method to style a looped component appropriately:

```
import React from 'react'
import reactCSS from 'reactcss'

const List = () => {
  const styles = reactCSS({
    'default': {
      item: {
        // applied by default
      },
    },
    'first-child': {
      item: {
        // applied to the first list item
      },
    },
    'last-child': {
      item: {
        // applied to the last list item
      },
    },
    'even': {
      item: {
        // applied to all even list items
      },
    },
    'odd': {
      item: {
        // applied to all odd list items
      },
    },
    'nth-child-3': {
      item: {
        // applied to the 3rd list item
      },
    },
  })

  ...
}
```