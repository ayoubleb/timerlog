### Usage

Following will print `[timerlog][generate-random-numbers][70ms] A million random numbers generated`

```js
// example.js
var timerlog = require('timerlog'); // `npm install timerlog`
                                    // works in Node.js and in the browser


var AMOUNT = 1e6;

var log_id = timerlog({
    message: 'A million random numbers generated',
    start_timer: true,
    tag: 'generate-random-numbers',
    measured_time_threshold: 10, // only print if measured time is greater than 10ms
    disabled: false // `disabled: true` -> do not print
});

let sum = 0;
for(var i=0; i<AMOUNT; i++) {
    sum += Math.random();
}

timerlog({
    id: log_id,
    end_timer: true,
});
```
