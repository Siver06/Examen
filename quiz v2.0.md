# Javascript Evaluation

1. What is a potential pitfall with using typeof bar === "object" to determine if bar is an object? How can this pitfall be avoided?

Because null is also an object, so bar must be verified no te be null. 

2. What will the code below output to the console and why?
   
```javascript
var myObject = {
    foo: "bar",
    func: function() {
        var self = this;
        console.log("outer func:  this.foo = " + this.foo);
        console.log("outer func:  self.foo = " + self.foo);
        (function() {
            console.log("inner func:  this.foo = " + this.foo);
            console.log("inner func:  self.foo = " + self.foo);
        }());
    }
};
myObject.func();
```
outer func:  this.foo = bar
outer func:  self.foo = bar
inner func:  this.foo = undefined
inner func:  self.foo = bar

self is variable that is stablished and remains, so in outer this an self are same instances of myObject, but in inner this is no longer instance for MyObject and is undefined.


3. What is the significance of wrapping the entire content of a JavaScript source file in a function block?

Because is a good programing technique and gives struture.

4. What will the code below output to the console and why?
```javascript
 (function(){
    return typeof arguments;
  })();
```

object, because the arguments referenced here is a general "object"

5. What will the code below output to the console and why?
```javascript
  var foo = {
    bar: function() { return this.baz; },
    baz: 1
  };
  (function(){
    return typeof arguments[0]();
  })(foo.bar);
```
undefined. Because this.baz is not defined until next line.

6. What will the code below output to the console and why?
```javascript
  var x = 1;
  if (function f(){}) {
    x += typeof f;
  }
  x;
```

1undefined. f is not defined but for the conditional is taken as true value so x becomes 1 + undefined string

7. What will the code below output to the console and why?
```javascript
/^(ab)$/.test('(ab)')
/^aa|bb$/.test('aaxx')
```


8. What is `use strict` used for?

Use to make olbigatory a strict parsing and error handling this to not ignore any error.

9. Rewrite the following code as Ecmascript Arrow Function
```
var double = function (i) {
  return i * 2;
};
```


10. Using the following code
    ```
    
    function Logger(level){
        this.level = level
    }
    
    Logger.prototype.log = function(msg){
        console.log(this.level + ' ' +msg)
    }
    ```
    
    print to the console the text: `INFO Message

msg = "Message";
console.log(msg);


11. Explain the difference between classical inheritance and prototypal inheritance.

The protptypal inheritance is the kind of inheritance that uses javascript and the protothype and functions have thos protothypes that can be inherited. 
