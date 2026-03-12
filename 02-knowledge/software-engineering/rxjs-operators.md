---
tags:
  - area/knowledge
  - area/software-engineering
---

# RxJS Operators

***takeUntil***
- Emits the values from the source Observable until such time as notifier emits its first value.

     this.paginationService.currentPage$
        .takeUntil(this.destroyed$)
        .subscribe(p => this.page = (p - 1));
     this.destroyed$.next(true);
    this.destroyed$.complete();
 const API_WATCH_LIST = (orgId) => `/organization/v3/${orgId}/watchlist`;

***concat***

- joins multiple Observables together, by **subscribing to them one at a time**

const getPostOne$ = Rx.Observable.timer(3000).mapTo({id: 1}); 
const getPostTwo$ = Rx.Observable.timer(1000).mapTo({id: 2}); 
Rx.Observable.concat(getPostOne$, getPostTwo$).subscribe(res => console.log(res));

E.g. When you need to send HTTP requests that should be in order.

https://www.learnrxjs.io/operators/combination/concat.html

***forkJoin***

Don’t let me know until all the Observables are complete, then give me all the values at once. 

E.g. when you need to run the Observables in parallel.

***Skip***

skips the first count items emitted by the source Observable.

***Take***

Emits only the first count values emitted by the source Observable.

**// Behavior Subject**

1. Needs an initial value
2. Upon subscription it returns the **last** value of the subject

For values that change over time

let currentNameSubject = new BehaviorSubject('Eric');
currentNameSubject.getValue();
currentNameSubject.next('Obama');
currentNameSubject.getValue();

let bSubject = new BehaviorSubject("a"); 

bSubject.next("b");

bSubject.subscribe((value) => {
  console.log("Subscription got", value); **// Subscription got b,** 
                                          **// ^ This would not happen** 
                                          **// for a generic observable** 
                                          **// or generic subject by default**
});

bSubject.next("c"); // Subscription got c
bSubject.next("d"); // Subscription got d

**// Regular Subject - Hot Observable**
1. Will not listen to values coming in until a subscription is called
2. Doesn’t hold a value

let subject = new Subject(); 

subject.next("b");

subject.subscribe((value) => {
  console.log("Subscription got", value); // Subscription wont get 
                                          // anything at this point
});

subject.next("c"); // Subscription got c
subject.next("d"); // Subscription got d

***Hot and Cold Observables***
Hot Observable more like a live performance - Will not get initial values at the start Cold Observable is watching a pre-recorded video

Publish method enables a cold Observable into a hot Observable
Connect on our hot Observable to start broadcasting values to its subscribers.

An **Observ­able**, by def­i­n­i­tion is a data **pro­ducer**. 
Albeit a spe­cial kind that can pro­duce data over time. 

A **Sub­ject** on the other hand can act as both — a data **pro­ducer** and a data **consumer**.

This implies two things.
1. A sub­ject can be sub­scribed to, just like an observ­able.
2. A sub­ject can sub­scribe to other observables.

If we can subscribe to it, then it is a producer 
subscribe will invoke our Observable

When an Observable produces values, it then informs the observer, calling .next() when a new value was successfully captured and .error() when an error occurs.

*// Here the same subject acs as a data consumer because it*
*// can subscribe to another observable*
observable.subscribe(subject);
           
        

const ALL_APP_STORES2 = (operatingSystems: boolean, countries: boolean, languages: boolean, devices: boolean, binaryFormats: boolean) => `/app-stores?supported-operating-systems=${operatingSystems}&supported-countries=${countries}&languages=${languages}&devices=${devices}&binary-formats=${binaryFormats}&sort=${sort}&order=${order}`;

\[ngClass\]="{ 'disabled': !isSubOrganisationEnabled }       this.appStoresService.getSortedAppStores(true, true, true, true, false, value,order).subscribe(
      data =>{
        this.appStoresFiltered = data;
      }
    )

const SORT_APP_STORES = (operatingSystems: boolean, countries: boolean, languages: boolean, devices: boolean, binaryFormats: boolean, name: string, order: string) => `/app-stores?supported-operating-systems=${operatingSystems}&supported-countries=${countries}&languages=${languages}&devices=${devices}&binary-formats=${binaryFormats}&name=${name}&order=${order}`;

  public getSortedAppStores(operatingSystems: boolean = true, countries: boolean = true, languages: boolean = false, devices: boolean = false, binaryFormats: boolean = false, name: string, order: string): Observable {
    return this.http
        .get(SORT_APP_STORES(operatingSystems, countries, languages, devices, binaryFormats, name, order))
        .map(appStoresArray => appStoresArray.map(appStoreJSON => new AppStore(appStoreJSON)))
        .catch(this.handleError.bind(this));
  }

**Resolver**: pre-fetching component data
A CrisisDetailResolver service could retrieve a Crisis or navigate away if the Crisis does not exist before activating the route and creating the CrisisDetailComponent

**Testing**
Angular test environment run change detection automatically - ComponentFixtureAutoDetect provider.

**xdescribe - test runner to exclude this group of test cases from execution.**
**fdescribe -** 

TestBed.createComponent method is synchronous. 
Won’t work with the external files e.g. './banner.component.html' from the file system before it can create a component instance. That's an asynchronous activity. 

*// async beforeEach*
beforeEach(async(() => {
  TestBed.configureTestingModule({
    declarations: \[ BannerComponent \], *// declare the test component*
  })
  .compileComponents();  *// compile template and css*
}));

**Use** [**aslogger.info**](http://aslogger.info)  **private** methods:  **component**\['getSelected'\]();
**public** methods:  **component.getSelected**();

**const** identity **=** x **=>** x;

**this**.activatedRoute.data
  .map(data **=>** data.appObservable)
  .takeUntil(**this**.terminateObservables$)
  .switchMap( identity )
  .subscribe( (\[ org, publicApp, managedApp \]) **=>** {
    *// ... same code follows*

fork the stream and describe two sets of effects - a function that navigates away

**const** identity **=** x **=>** x;

**const** \[ publicApp$, other$ \] **=** **this**.activatedRoute.data
  .map(data **=>** data.appObservable)
  .takeUntil(**this**.terminateObservables$)
  .switchMap( identity )
  .partition( (\[ org, publicApp, managedApp \]) **=>** managedApp.appid **===** 0 **&&** **this**.publicApp );

*// pseudocode below, these functions would just contain the current code*
publicApp$.subscribe( sendToWatchlist );
other$.subscribe( updateState );

## Related
- [[software-engineering-moc]]
- [[protractor-e2e-testing]]
- [[query-annotation]]
- [[es6-new-features]]
