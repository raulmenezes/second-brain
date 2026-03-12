---
tags:
  - area/knowledge
  - area/software-engineering
---

# Props are state’s immutable

State in Parent components are passed down as immutable props to Children

one-way data pipeline

children communicate with parents by calling functions that are
handed to them via props

manipulate the virtual
representation and let React take care of changing the browser’s DOM.

Actual-DOM
- It’s hard to keep track of changes - it can become difficult to keep track of current (and prior)
state of the DOM to manipulate it into the form we need.
- It can be slow - modifying the actual-DOM is a costly operation, and modifying the DOM on
every change can cause significantly degrade the performance.

Virtual DOM will:
• use efficient diffing algorithms, in order to know what changed
• update subtrees of the DOM simultaneously
• batch updates to the DOM

JSX is syntactic sugar to call React.createElement

ReactElement is a representation of a DOM element in the Virtual DOM.

## Related
- [[software-engineering-moc]]
- [[shared-module]]
- [[shared-module]]
- [[new-notes-from-handbook-https-medium-freecodecamp-org-the-definitive]]
