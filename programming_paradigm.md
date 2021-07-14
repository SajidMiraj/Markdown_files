# Parallel, Concurrent, Synchronous, Asynchronous, Blocking, Non-blocking
*NOW THAT I KNOW*  
`Date: 10Jun, 2021`

## PARALLEL PROGRAMMING
Parallel programming paradigm utilizes multiple CPU Core to solve a problem. It's a physical phenomenon, codes run on multiple physical core.

## CONCURRENT PROGRAMMING
Concurrent programming utilizes a single CPU Core in a way that mimic multiple things done at the same time.  

### How does if do it?
CPU's are fast in many magnitude then others peripheral of a Computer System. e.g, RAM, I/O Devices, Disks. Almost all programme consists operation that's at same point of a program lifetime uses these slow peripherals. Concurrent paradigm use this as a means of doing other CPU related thing when part of a programs code wait for these slow devices to response back with data. Normally, program wait for this so, CPU can't do anything at that moment of time, Concurrency, utilizes CPU by not waiting.


## Synchronous
As the name suggest, it's a way of doing things sequentially. It's not a programming paradigm, rather it's a code waiting style for a particular language.

## Asynchronous 
As the name suggest, it's a way of doing thing not sequentially, but not totally randomly either. It's a coding style. Different programming languages uses mixture of these *Synchronous | Asynchronous* paradigm for waiting code.

**Example of Synchronous Code**
```javascript
let x = do-some();
console.log(x)

let y = do-other();
console.log(y)
```

**Example of Asynchronous Code**
```javascript
//take 15 sec to complete
do-some().then((x) => {
    console.log(x)
})

//take 10 sec to complete
do-other().then((x) => {
    console.log(y)
})
```

Synchronous Code must finish *x-function* before starting *y-function*. This codes flow is sequential.  
In case of, Asynchronous Code, after running *do-some()*, we jump to *do-other()* without caring for *printing x* in console. We might expect *x* finish first but, it won't happen. Because, *do-some()* took 15sec to completely execution.  
Synchronous code would take 25sec to complete, but Asynchronous code takes only 15sec to complete.

## Blocking & Non-blocking 
Blocking is when upper part of a code blocks the lower part before it finishes, as you just saw in previous page code example. Non-blocking is the opposite to that.  

Non-blocking unites a paradigm, not a code writing style. It's moves like a adjective to async, sync code style .