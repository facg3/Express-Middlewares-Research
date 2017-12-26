# Express-Middlewares-Research

### What are express middlewares ?
#### Middlewares : 
It's functions have accsess on the Request , the Response and the next function in the application’s request-response cycle

##### Midldleware functions : 
-  Excute any code .
-  Make changes to the request and the response objects.
-  End the request-response cycle.
-  Call the next middleware .

#### The following figure shows the elements of a middleware function call : 

![pic](https://serving.photos.photobox.com/203490990ba76b95fbb5507e88956a7c2c58c644500a8f7fda1c9ab651ef0f2d22524852.jpg)


## What functionality do they provide?
Up until to this point, we knew that middlewares are functions, with additional super ability that fires the next middleware.

And as just as the other functions do, it do some codes!

### Functionalitis:
Express for JS is a framework built upon the idea of Middlewares, by that, we can say: that we can use them to do anything we want.
1. Middlewares on Requests: Using ``` app.use() ``` we can fire a middleware, or a bunch of them once a request is received on the server side, and do some changes on the request body, headers and even more.
2. Middlewares on Response: And again, middlewares are to be used before sending back a response to the front-end(client side), e.g. there are middlewares that compress the body of the response.
3. Next: the third functionality that middlewares provide, is the ability to fire a long sequence of which, using ``` next() ```, which is the third argument besides the request and response, when a ``` next() ``` command is executed, it fires the next middleware coming beyond it, and that is how it keeps going on..

----------

## What are some examples of useful express middleware? and how do you use them?
1. bodyParser: Is used to parse what ever a request holds on it is body into a JSON object, then replaces the request body with the new data.
2. compression: Is used to minimize(compress) response body to a smallest pack of data, with the ability to control whether some response should go through that middleware or not, using ``` Cache-Control : no-transform``` on the required response header.

### Curious about more? check: [expressjs github pages](https://github.com/expressjs)

### How to use a certain middleware?
#### body-parser:
1. First of all, we have to install it in our project dependencies list, using:
```
npm install body-parser
```
2. Require it into your express application:
``` javascript
const bodyParser = require('body-parser');
```
3. Body parser middleware has lots of different methods which we can use in our express application, e.g.
3. a. bodyParser.json(): Is used to parse what ever a request holds on it is body into a JSON object, then replaces the request body with the new data.
3. b. bodyParser.urlencoded(): Accepts only request body that is encoded with (UTF-8) and transfers it to a Key-Value object replacing the request body.
3. c. Implementing:
``` javascript
const parseJson = bodyParser.json();
const urlencoded = bodyParser.urlencoded({ extended: false });
// extended: false > means that values inside the object can be either a string or an array.

app.use(parseJson);
app.use(urlencoded);
// new OBJECT TYPE data are stored in (request.body)
```

References :   
using middleware : http://expressjs.com/en/guide/using-middleware.html   
writing middleware : https://expressjs.com/en/guide/writing-middleware.html   
modules midlleware : https://expressjs.com/en/resources/middleware.html   
