# Research1

Is about several points:
a - (MAP, SwitchMAP, MergeMAP, throwError, ForkJOIN) in RXJS.\n
b - (HTTPEXCEPTION) in NestJS.
c - (KEY) in DatastoreGC.

### RxJS:

#### MAP

##### definition - This function is going to edit each element in the observable and return the values in observable.

##### prototype - map (project_function, this (optional))

**project_function:** is the function that is applied for each value of stream.
**this:** is optional define what this is in project_function.

**Return** - observable values

#### MergeMAP

##### definition - the function is going to project each value of observable and merge all otputing them

##### prototype - mergeMap (project_function, resultSelector, concurrent)

**project_function** - is the function that is applied for each value of stream.
**resultSelector**: default undefined.
**concurrent**: default infinity descripes the number of observable values to be inputed.
**Return**: observable values.

#### SwitchMAP

##### definition - the function is going to project each value of observable and emit only the most recent edited value(last value).

##### prototype - switchMap (project_function, resultSelector)

**project_function**- is the function that is applied for each value of stream.
**resultSelector:** default undefined.
**Return:** most recently edited value.

#### forkJoin

##### definition - this function accepts an array of observables and return observable of last value of each stream.

##### prototype - forkJoin(args)

**args:** array of observables.
**Return:** last value in each passed observable

#### throwError

##### definition - this function creates an observable and from it create error and return error to user upon subscription.

##### prototype - throwError(errorFactory).

**errorFactory:** the error contains the error message
**Return:** error upon subscription.

### NestJS

#### HTTPEXCEPTION

##### definition - a class exposed from @nest/common package that work with API's

##### prototype - HTTPEXCEPTION(err_message, status_code)

**err_message:** is a message sent as response to the client (ex: login failed)
**status_code:** the code of header of site.

**!important** HTTPEXCEPTION include builtins that can be used as BADREQUESTEXCEPTION, UNNAUTHORIZEDEXCEPTION and etc
they are used instead of using HTTPEXCEPTION we use this builtin depending on the error type.

### DataStore

#### KEY

##### definition - the key is the identifier that must be unique and used to identify the mysql database as in sql

**to define ex:** const key = Datastore.key({path:[kind, id]});
**to define nameKey ex:** const nameKey = Datastore.key({path:[kind, name]});

where this key is then added to the data of entity and inserted to the database.
