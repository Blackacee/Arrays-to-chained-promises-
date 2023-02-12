# Arrays-to-chained-promises-
 
[1, 3, 5, 7, 9].reduce((seq, n) => {
 return seq.then(() => {
 console.log(n);
 return new Promise(res => setTimeout(res, 1000));
 });
}, Promise.resolve()).then(
 () => console.log('done'),
 (e) => console.log(e)
);
// will log 1, 3, 5, 7, 9, 'done' in 1s intervals
