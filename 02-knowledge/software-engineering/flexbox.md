---
tags:
  - area/knowledge
  - area/software-engineering
  - topic/docker
---

# Flexbox

A flex container expands items to fill available free space, or shrinks them to prevent overflow

parent element - flex container 
children - flex items

Regular layout is based on both **block** and **inline** flow directions
Flex layout is based on "flex-flow directions"

**Properties for the parents**

**Flex-direction**
Laying out either in horizontal rows or vertical columns.

**Flex-wrap**
Flex items will all try to fit onto one line - alters the width of the children to fit one line

**Flex-flow**
shorthand flex-direction and flex-wrap
Default is ***row*** ***nowrap***

**justify-content**
alignment along the main axis

![[attachments/screen-shot-2018-01-19-at-15-17-51.png]]

.container {
  display: flex; /* or inline-flex */
  flex-direction: row | row-reverse | column | column-reverse;
  flex-wrap: nowrap (default) | wrap | wrap-reverse;

  **flex-flow**:  || 
  justify-content: flex-start | flex-end | center | space-between | space-around | space-evenly;
}

**Properties for the children**

**order**
Controls the order in which they appear in the flex container

**Flex-grow**
Amount of the available space inside the flex container the item should take up.

**flex-shrink**
Ability for a flex item to shrink if necessary.

**flex-basis**
Defines the default size of an element before the remaining space is distributed
if set to **0**, the extra space around content isn't factored in. 
If set to **auto**, the extra space is distributed based on its **flex-grow**

**Flex**

Shorthand for **flex-grow**, **flex-shrink**, **flex-basis**
The second and third parameters (flex-shrink and flex-basis) are optional
Default is 0 1 auto

**align-self**
allows the default alignment (***align-items***) to be overridden for individual flex items. 

*float, clear and vertical-align have no effect on a flex item*

![[attachments/screen-shot-2018-01-19-at-09-49-45.png]]

*item* {
  order: ; /* default is 0 */
  flex-grow: ; /* default 0 */
  flex-shrink: ; /* default 1 */
  flex-basis:  | auto; /* default auto */
  
  flex: none | \[  ? ||  \]
}

  height: 440px;
  overflow-x: hidden;
  overflow-y: auto;

this.listOfCompatible = this.listOfCompatible.concat(this.allCompatible.splice(0,9));
      

## Related
- [[software-engineering-moc]]
- [[lombok]]
- [[redux]]
