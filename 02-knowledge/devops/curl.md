---
tags:
  - area/devops
  - area/knowledge
  - topic/networking
---

# CURL

- -X: set the HTTP method
	- curl -X POST url
	- curl -X POST -d '{"answer":42}' url

- -d: set the request body, as a string, for PUT and POST requests
	- curl -X POST -d '{"answer":42}' -H "Content-Type: application/json" url
	- curl -X PUT -d '@data.json' -H "Content-Type: application/json" url
		- @ prefix tells curl to load the request body from the 'data.json' file

- -H: set a request header
	- curl -H "Authorization: my-secret-token" url

- -u: Auth credentials for basic auth
	- curl -i -u "user:pass" url

- -O: store the response body in a file
	- curl -OL url

- -i: show the raw response, including response headers

## Related
- [[devops-moc]]
- [[architecture]]
- [[azuruw]]
- [[module-1]]
