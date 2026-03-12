---
tags:
  - area/knowledge
  - area/software-engineering
  - topic/angular
  - topic/javascript
  - topic/spring
  - topic/testing
---

# RxJX   Reactive Programming

“asynchronous and event-based programs using observable sequences and fluent query operators”

Library easily create and manipulate **streams of events** and **data**. 
Allows for Developing readable asynchronous code

Problem:
Large asynchronous applications - Callback hell

**Promises**, **Generators**, and **async/await**. 
There is another solution, and it is called **RxJS**.

Create streams from events and other sources of data. 
Able to merge, mash, split, and more with this data.  Collection of events or pieces of data over a period of time. 

Observables are sometimes multicast.
Observables are usually async.

 
In Plain JavaScript
 // Get stream of button clicks
 const btnClickStream = Rx.Observable
		 .fromEvent(addLocationBtn, 'click')  		.forEach(val => console.log('btnClickStream val', val));  **fromEvent** to create a stream from the click event  **forEach** adds a subscriber to the stream
  // Get stream of zip codes
const zipInputStream =
  Rx.Observable
    .fromEvent(zipcodeInput, 'input')
    .map(e => e.target.value)
    .filter(zip => zip.length === 5)
    .forEach(val => console.log('zipInputStream val', val)); 
 **filter** remove all values that does not pass condition
 subscribe happens synchronously whereas the then (Promise) happens asynchronously

Many ways to create Observable  Observable.fromEvent 
Observable.to
Observable.from -> Convert a Promise to Observable

## Related
- [[software-engineering-moc]]
- [[directive]]
- [[6-key-areas-spring-framework]]
- [[jpa-and-spring-data]]
