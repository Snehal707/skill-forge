---
name: create-react-component
description: Create and implement a reusable React component with props and state
version: 1.0.0
metadata:
  skill_forge:
    domain: "react"
    generated_at: "2026-02-26T10:00:00Z"
    validation_passed: true
    sources_used: 5
  hermes:
    tags: [react, javascript, frontend, components, ui]
    category: frontend
---

# Create React Component

## When to Use
When you need to build a reusable UI component in React that accepts props and manages its own state.

## Prerequisites
- Node.js installed (version 14+)
- npm or yarn package manager
- Basic JavaScript knowledge
- React project already initialized (`create-react-app` or similar)

## Procedure
1. Create component file: `touch src/components/MyComponent.js`
2. Import React: Add `import React, { useState } from 'react';` at the top
3. Define component function:
   function MyComponent({ title, onClick }) {
     const [count, setCount] = useState(0);
     
     return (
       <div>
         <h2>{title}</h2>
         <button onClick={() => setCount(count + 1)}>
           Clicked {count} times
         </button>
         {onClick && <button onClick={onClick}>Action</button>}
       </div>
     );
   }
   ```
4. Export component: Add `export default MyComponent;` at the bottom
5. Import in parent: `import MyComponent from './components/MyComponent';`
6. Use component: `<MyComponent title="My Title" onClick={handleClick} />`

## Verification
- Component renders without errors in browser
- Props are correctly passed and displayed
- State updates trigger re-renders
- Console shows no React warnings

## Pitfalls
- Forgetting to export the component
- Not handling undefined props gracefully
- Mutating state directly instead of using setState
- Missing key props when rendering lists

## Sources
- https://react.dev/
- https://legacy.reactjs.org/
- https://github.com/facebook/react
```