---
tags:
  - area/knowledge
  - area/software-engineering
  - topic/javascript
---

# Shared Module


A shared module can expose reusable components, directives and pipes across multiple feature modules while keeping singleton services in the CoreModule.

Avoid specifying app-wide singleton providers in a SharedModule. Intentional singletons are OK. Take care.

Why? A lazy loaded feature module that imports that shared module will make its own copy of the service and likely have undesirable results.

Why? You don't want each module to have its own separate instance of singleton services. Yet there is a real danger of that happening if the SharedModule provides a service.

Unless - the consumers of the service aren't impacted by new instances.

**Core Module**

CoreModule will contain singleton services. When a lazy loaded module imports these, it will get a new instance and not the intended app-wide singleton.

Do gather application-wide, single use components in the CoreModule. Import it once (in the AppModule) when the app starts and never import it anywhere else. (e.g. NavComponent and SpinnerComponent).

export all symbols from the CoreModule that the AppModule
E.g.
Logger
Nav
Spinner

Prevent re-import of the core module

## Related
- [[software-engineering-moc]]
- [[useful-node-modules]]
