React uses tree-like (Fiber-tree) internally to calculate the minimum DOM updates and commit them in Commit phase. In this post, we'll figure out how exactly React dows the initial mount (first-time-render). Render to be more specific, we'd like to know how React Construct the DOM from code bellow.
```typescript
import { useState } from 'react'

function Link() {
  return <a href="https://jser.dev">jser.dev</a>
}

export default function App() {
  const [count, setCount] = useState(0)
  return (
    <div>
      <p>
        <Link/>
        <br/>
        <button onClick={() => setCount(count => count + 1)}>click me - {count}</button>
      </p>
    </div>
  );
}

```

### 1. Brief introduction on Fiber Architecture
![[Pasted image 20251125230728.png]]
Fiber is the architecture of how React holds internal representation of the App state. It is a tree-like structure consisting `FiberRootNode` and `FiberNodes`. There are all kinds of FiberNode and some of them have backing DOM node - HostComponent.

React runtime tries its best to maintain and update the Fiber Tree and sync the host DOM with minimum updates.
#### 1.2 `FiberNode`
FiberNode means all nodes other than FiberRootNode, some of important properties are: 
	1. `tag`: FiberNode has many sub type differentiated by `tag`. For example, FunctionComponent, HostRoot, ContextCosumer,MemoComponent, SuspenseComponent, etc.
	2. `stateNode`: it points to the other backing data, for `HostComponent`, `stateNode` points the actual backing DOM node.
	3. `child`, `siblind` and `return`: these together form a tree-like structure.
	4. `elementType:` which is the component function or instrinsic HTML tag we provide.
	5. `flags`: to indicate the updates to apply Commit phase. `subtreeFlags` is for its subtree.
	6. `lanes`: to indicate the priority of pending updates. `childLanes` if for its subtree.
	7. `memoizedState`: points to its important data, for FunctionComponent it means the hooks.
