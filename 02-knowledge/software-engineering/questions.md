---
tags:
  - area/knowledge
  - area/software-engineering
  - topic/angular
  - topic/javascript
  - topic/spring
  - topic/testing
---

# Questions

**AOT -“Ahead of Time compilation”** compiles the angular components and templates to native JavaScript and HTML during the **build time** instead of **run-time.**
The compiled HTML and JavaScript are deployed to the web server so that the **compilation** and **render** **time** can be **saved by the browser**. 
It is the big advantage to improve the performance of applications.

**Lazy Loading** Lazy loading enables us to load only the module user is interacting and keep the rest to be loaded at run-time on demand. speeds up the application initial load time by splitting the code into multiple bundles and loading them on demand.  **Securities Threats** Avoid using or injecting dynamic HTML content to your component.
Avoid using external URLs if not trusted.
Prevent XSRF attack by restricting the REST APIs.
 **Isolated unit tests**
Check-up an instance of a class itself without using any Angular dependence or any injected values. Don't realize how components interact with Angular and also don't realize how a component class interacts with its own template or components. Angular Pipes and Services - we should write isolated unit tests! https://angular.io/guide/testing  **Access a Global Variable** 
Import and Use the Global Variables in the Component  **Renderer and ElementRef**
Used for DOM Manipulation 
Used together to get full platform abstraction.  **Directives**  are used to add behavior to existing DOM elements. design a reusable   **@Output**  binds a property of a component to send the data from child component to parent component (EventEmitter)  @[Output](https://angular.io/api/core/Output)() onVoted = new [EventEmitter](https://angular.io/api/core/EventEmitter)(); vote(agreed: boolean) {
	this.onVoted.emit(agreed);
}

## Related
- [[software-engineering-moc]]
- [[query-annotation]]
- [[spring-framework-questions]]
- [[elasticsearch]]
