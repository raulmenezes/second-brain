---
tags:
  - area/knowledge
  - area/software-engineering
  - topic/angular
  - topic/docker
  - topic/javascript
  - topic/testing
  - topic/travel
---

# Redux

Single Object that holds state of the applications

**Actions** - 

Type property to define an action
{type: ‘MARK_READ’}

**Reducer**
Function that specifics how the state will change

Does not modify the state - Creates a new one

All of them are Pure function

- Same input get same output - no side effects
Does not modify its argument - e.g. count++

//Making backend calls to a server

Random or Date is an impure function

Not going to modify the original state -
function reducer (state, action){
	swtich(action.type){
		case: ‘Increment’:
			return { count:  state.count + 1};

Alway return a new state
Easy to test - Simple input and output
Implement features
Time Travel Debugging - See how different actions 
Complex data structures - 

Two Redux Libraries to do 
ngrx-store - RX 
ng2-

npm install redux @angular-redux/store --save

{
  apis: {     // data from various services
    api1: {},
    api2: {},
    ...
  }, 
  components: {} // UI state data for each widget, component, you name it 
  session: {} // session-specific information
}

Redux Dev Tools
https://chrome.google.com/webstore/detail/redux-devtools/lmhkpmbekcpmknklioeibfkpmmfibljd?hl=en

Redux-logger middlewares 
npm install --save redux-logger

npm install redux-localstorage --save

**reduce-reducers**
Two reducers to work on the *same* portion of the state object

export default function reduceReducers(...reducers) {
  return (previous, current) =>
    reducers.reduce(
      (p, r) => r(p, current),
      previous
    );
}

const rootReducer = reduceReducers(counter, decrementer);

combineReducers
The resulting reducer calls every child reducer, and gather their results into a single state object.
The shape of the state object matches the keys of the passed reducers

 	*.	HttpErrorResponse {headers: HttpHeaders, status: 200, statusText: "OK", url: "https://qa.appscatter.tools/coreapi/usermanagement/organization/create", ok: false, …}*

-  
	- error : 
		- error : SyntaxError: Unexpected token d in JSON at position 1 at JSON.parse () at XMLHttpRequest.onLoad (webpack-internal:///../../../common/esm5/http.js:2289:51) at ZoneDelegate.invokeTask (webpack-internal:///../../../../zone.js/dist/zone.js:425:31) at Object.onInvokeTask (webpack-internal:///../../../core/esm5/core.js:4941:33) at ZoneDelegate.invokeTask (webpack-internal:///../../../../zone.js/dist/zone.js:424:36) at Zone.runTask (webpack-internal:///../../../../zone.js/dist/zone.js:192:47) at ZoneTask.invokeTask \[as invoke\] (webpack-internal:///../../../../zone.js/dist/zone.js:499:34) at invokeTask (webpack-internal:///../../../../zone.js/dist/zone.js:1540:14) at XMLHttpRequest.globalZoneAwareCallback (webpack-internal:///../../../../zone.js/dist/zone.js:1577:21) text : "8d81c585-d01a-469d-8574-f03de121db97" __proto__ : Object 
	- headers : HttpHeaders
		- lazyInit : *ƒ ()* lazyUpdate : null normalizedNames : Map(0) {} __proto__ : Object 
	- message : "Http failure during parsing for https://qa.appscatter.tools/coreapi/usermanagement/organization/create" name : "HttpErrorResponse" ok : false status : 200 statusText : "OK" url : "https://qa.appscatter.tools/coreapi/usermanagement/organization/create" __proto__ : HttpResponseBase 

State Interface in reducer State -> feature.reducer.ts 
 All States -> app.state.ts 

State folders by feature or function ?

Move by function approach to a by feature approach
Feature Angular style guide to organise it by feature - lazy loading and easy to read

Move toward a Presentational and Container Component - mindset

## Related
- [[software-engineering-moc]]
- [[shared-module]]
- [[shared-module]]
- [[cypress-setup]]
