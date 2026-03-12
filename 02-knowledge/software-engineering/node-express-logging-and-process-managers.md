---
aliases:
  - production-ready-node-and-express-logging-properly-using-module
note-type: permanent
tags:
  - area/knowledge
  - area/software-engineering
  - topic/angular
  - topic/database
  - topic/javascript
  - topic/monitoring
  - topic/testing
---

# Node, Express Logging, and Process Managers

Short reference note on basic Node API logging and process management choices.

## Logging

write to database ?
- https://medium.freecodecamp.org/how-to-log-a-node-js-api-in-an-express-js-app-with-mongoose-plugins-efe32717b59

## Process Managers

Don’t use - node app.js 
As it will be offline and need a restart on a crash

Popular process managers for Node:
- StrongLoop Process Manager
- PM2
- Forever

## Related
- [[software-engineering-moc]]
- [[javascript-and-v8-notes]]
- [[jpa-and-spring-data]]
- [[cypress-setup]]
