# Javascript Advance Concepts 

`Date: 12/07/2021`

## Arrow Function & It's use :-
- Firstly, you declare a meaningful variable.
- `() space => {}` Follow this kind of syntax.
- All of your logics and code written between `{}` curly-brace.

Example, 
```javascript
const funcEvenOdd = (num) => {
    return num%2 === 0 
}

console.log(funcEvenOdd(parameter));
```
`Output: true or false`

- here, this code gives you, is even or odd number?
- if parameter=10, this is even number. **function save true value**  and `output = true`


## Closure & It's use :-
*i write it later*

## Synchronous & Asynchronous in JS :-

### Synchronous
- Synchronous code follows the step by step code execution.
- It blocked the bottom codes
- if any function runs, first the function finish and then next lines of code will be execute.

### Asynchronous
- It doesn't blocked the bottom codes.
- **There are 3 ways to written Asynchronous codes**  
`Async/Await`  
`Callback`  
`Promise`  

## AJAX & It's use :-
- **AJAX** full-form is Asynchronous Javascript and XML (extensible Markup Language)
- It's a method of send and fetch data without full page loading.
- **There are five methods on AJAX or xmlHttpRequest (XHR) object**  
`open`, `onprogress`, `onreadystatechange`, `onload`, `sent`


### `open`
- This method open the XHR object.
- It takes 3 arguments in its parameter.
- 1st argument is request type. `GET` or `POST`
- 2nd argument is `URL`. That's means where from comes this request data.
- 3rd argument is `boolean` type. 
If this request types of `async` then, it takes `true` and If request is `sync`, it takes `false`


### `onprogress`
- It is an optional method.
- It's gives us the status of this request.

### `onreadystatechange`
- It's gives us the status of changing every state of the XHR request
- There are `5 state in XHR`. All those hold in `readyState` function.
It counts <ins>0 to 4</ins>.  
`0: request not initialized`, `1: server connection established`,
`2: request received`, `3: processing request`, `4: request finished and response is ready`
- It's has also a function called `status`. It checked the `http status code` like `200 or 403 either 404`

### `sent`
- When every works perfectly, This `sent` method sent the request on *Server* and gives us the response data.


### How to create an ajax function :-
1. Create ajax object.
2. Initiated this object or open the object.
3. Check the progress of XHR. <ins>(Optional)</ins>
4. Check those state-changing progress of XHR. <ins>(Optional)</ins>
5. Onload this object.
6. sent the request for responding.


**Example of GET Request:-**  

```javascript
//GET request
function appsWithAJAX() {
        // 1. Create ajax object.
        let xhr = new XMLHttpRequest();

        // 2. Initiated this object or open the object.
        xhr.open('GET', 'https://jsonplaceholder.typicode.com/posts/1', true); 
        //1st arg = method type, 2nd arg = url, 3rd arg = is it async process or sync process? if async = true; is it is sync = false

        // 3. Check the progress of XHR. (Optional)
        xhr.onprogress = function () {
                alert('This is processing data')
        }

        // 4. Check those state-changing progress of XHR. (Optional)
        xhr.onreadystatechange = function () {
                console.log('This is the status', this.readyState);
        }

        // 5. Onload this object.
        xhr.onload = function () {
                (this.status === 200 && this.readyState === 4) ? console.log(this.responseText) : console.log('Error Generated! ')
        }

        // 6. sent the request for responding.
        xhr.send();
}

// call the function
appsWithAJAX()
```


**Example of GET Request:-**  

```javascript
function appsWithAJAXPost() {
    console.log("started !");

    let xhr = new XMLHttpRequest();

    xhr.open('POST', 'URL', true);

    xhr.getResponseHeader('content-type', 'application/json'); //for POST JSON data

    xhr.onload = function () {
	    (this.status === 200 && this.readyState === 4) ? console.log(JSON.parse(this.responseText)) : console.log('Error Generate! ');
    }

    let postData = { "key": "value" }; //json data for posting.
    xhr.send(JSON.stringify(postData));
}

appsWithAJAXPost()
```


## Promise in Javascript :-
- Promise is an object in javascript.
- In JS, promise have 3 state `1. resolve`, `2. reject`, `3. pending`
- When, promise function runs, it's has in `pending` state.
- If promise function successfully done it's job, we will get `resolve`.
- Or if promise function not done it's job, we will get `reject`.


### Implement Promise in JS :-
1. We need to create a function.
2. This function will `return` us an `new Promise` object.
3. Under the `new Promise` object, we need to write a callback function (arrow function) and it takes 2 parameter `1. resolve`, `2. reject`.
4. In this arrow function, we implements our coding logic and use promise efficiently. Like, we will be request a server for response. If server gives us proper response, we will printed `resolve function`. Otherwise, we will be printed `reject function` <br> <br>
6. After implementing `promise function`, we will call this `promise function`. 
7. `function().then` takes a callback of the `resolve` of this promise and .catch will takes also a callback of the `reject` of this promise  

**Example Of Promise Code**  

```javascript
const x = 10;

function promiseFunction() {
    return new Promise((resolver, rejector) => {  //resolver & rejector are the peremeter of this callback.
        // if x=true, we will get resolve of the promise
        // if x=false, we will get reject of the promise

        (x>0) ? resolver("resolve: x is bigger than 0") : rejector("reject: x is not bigger than 0")
    });
};

// call the promise function
promiseFunction().then((resolver) => 
console.log(resolver)).catch((rejector) => 
console.log(rejector));
```

### Fetch data using Promise :-
```javascript
// GET Request
const GetPromise = function() {
    let url = 'https://api.github.com/users';
    fetch(url).then((response) => response.json()).then((data) => console.log(data));
}
// call the fucntion
GetPromise();

// POST Request
const PostPromise = function() {
    let postDataToServer = {"name":"sajidmiraj","salary": 75000,"age": 18}; //sompal of posting data    
    let postdata = {
        method: 'POST',
        header: {'content-type': 'application/json'},
        body: JSON.stringify(postDataToServer), //convert json to string
    }
    
    let url = 'http://dummy.restapiexample.com/api/v1/create';
    fetch(url, postdata).then((response) => response.json()).then((data) => console.log(data));
}

// call the fucntion
PostPromise();
```


## Async/Await in JS :-
- It's an non-blocking advance `Promise` in Javascript.

```js
async function getApi() {
    let url = 'https://api.github.com/users';
    let response = await fetch(url);
    let jsonData = await response.json();
    console.log(jsonData)
};

// call the function
getApi();
```


## Class in JS :-
- Class is a blueprint or something like templates. 
- using it, you can implementing more objects included in your code.

### Implement a `class` :-
- first of all, you need to write the keyword of `class` and *given a name* Of your class and last write `{}`
- All of your code will be inside the `{<code>}`
- then, write a keyword of `constructor`. It's syntax full of JS function and it takes arguments.
- Inside the `constructor`, you code like `this.<argument> = argument`.
- You can also create your own methods inside the class but outside of constructor
- Creating it, first of you write your method name using syntax `<methodName> () {return <something>}`.
- under the function, you write `return` keyword for your method code. 
- you can also create *static methods* indise the class using `static` keyword.
- creating it, you need to follw the syntax. `static <function name> () {<your-code>`

### Use class in Code :-
- first you need *crete a variable* and the variable value will be `new <class-name> ()`
- Inside the `()`, you need to pass peremeter that you define under `constructor`.
- You can also use *methods* using this syntax `variableName.<method>()`
- If you need to use *static methods*, you following this syntax `<class-name>.<method>()` 

**Example code of `class`**  

```js
class Users{    //class name
    constructor (name, age) {   // constructor is like a function
        this.name = String(name);   //argument
        this.age = Number(age)  
    }
    
    userFullInfo (){    //it is a method and also a function that return something.
        return `this user name: ${this.name} and he/she is ${this.age} years old`
    }

    // static mathods
    static companyName(){
        return "UNIman"
    }
}

const sajid = new Users("sajid", 18);   //varibale with new <className>
console.log(sajid.userFullInfo());  //use the method
console.log(Users.companyName())    //use static method
```

### Inherit class in JS :-
- if you need inherit any class, inside the other class, you need to *copy whole the* `construcor`.
- your new `construcor`contains with old arguments and new arguments too.
- Then, under the `constructor`, you need to write `super` keyword  and *pass all argument of privious*`construcor`.

**Examples of inharit `class`**  
```js
// This class inherit from User class.
class NewUser extends Users{
    constructor (name, age, location){  //under its constructor, it need previous arguments + new arguments
        super (name, age);  //copy the whole contructor and rename by 'super'
        this.location = location
    }
}

const xyz =  new NewUser("xyz", 16, "Shibjong")
```