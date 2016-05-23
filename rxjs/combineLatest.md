## Problem:
Need to combine two streams into one which signalises changes from both of them.

## Solution:
`combineLatest`

```
let src1 = Rx.Observable.interval(30);

let src2 = Rx.Observable.interval(200);

let result = Rx.Observable.combineLatest(
  src1,
  src2,
  (first, second) => ({first, second})
);

result.subscribe(val => console.log(val));
```

To `combineLatest` you can pass sources you want to combine and a merger function which will know how to join the events from all streams.
It's usage is similar to use of selectors from redux/reselect projects.
