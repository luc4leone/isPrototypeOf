## Beasts challenge #5: isPrototypeOf

In AccountingJS 8 and 9, you learned about JavaScript's prototype system. This challenge builds on those videos.

Write a function, isPrototypeOf, that works just like Object.prototype.isPrototypeOf. Since your solution will be called as a function rather than a method, the way you use it will be slightly different, but the outcome should be the same.

Obviously, don't use Object.prototype.isPrototypeOf in your solution, but feel free to use other methods on Object.prototype.


```javascript
var canine = {
  bark: function() {
    console.log('bark');
  }
};

var dog = Object.create(canine);
dog.fetch = function() {
  console.log('fetch');
};

var myDog = Object.create(dog);
var empty = Object.create(null);

// These two lines are equivalent.
dog.isPrototypeOf(myDog);  // native function returns true
isPrototypeOf(dog, myDog); // your function does the same

// These two lines, similarly should return the same thing.
dog.isPrototypeOf(empty);  // native function returns false
isPrototypeOf(dog, empty); // your function does the same

// This should work too.
Object.prototype.isPrototypeOf(myDog);  // native function returns true
isPrototypeOf(Object.prototype, myDog); // your function does the same

// Also make sure that your function will work for any number of prototype links.
isPrototypeOf(canine, myDog) // true
```

As usual, post your solutions below and good luck! And write tests first!