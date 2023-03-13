# Javascript Scheduling Code Order

## Question
Running order of below codes
```javascript
setTimeout(() => console.log('timeout'), 5000);
setInterval(() => console.log('interval'), 5000);
setImmediate(() => console.log('immmediate'));
console.log('log');
```

## Answer
```bash
log
immmediate
timeout
interval
```

## Reason
```
n JavaScript, the setImmediate, setTimeout, and setInterval functions are used for scheduling code to be executed later.

setImmediate schedules a callback function to be executed on the next iteration of the event loop. It has higher priority than setTimeout and setInterval.

setTimeout schedules a callback function to be executed after a specified delay in milliseconds. The delay can be zero or greater. setTimeout has a lower priority than setImmediate, so if setImmediate and setTimeout are both scheduled for execution at the same time, setImmediate will be executed first.

setInterval schedules a callback function to be executed repeatedly with a fixed time delay between each execution. If setInterval and setImmediate are both scheduled for execution at the same time, setImmediate will be executed first.

However, it's important to note that the order of execution also depends on the current state of the event loop and the workload of the system. So, it's possible that the order of execution may be different in different circumstances.
```
