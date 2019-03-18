# Bailey



# 1)Write a multiplication function in javascript to use like this.

function mul(x) {
return function (y) {
return function (z) {
return x*y*z;
}
}
}
console.log(mul(2)(3)(4));

# 2)Which of the following code snippet append an element value at the end of the array, arr?

a) arr[arr.length+1] = value

# b) arr[arr.length] = value===> Correct Answer

c) arr[arr.length - 1] = value

d) arr = arr + value 

# 3) JavaScript: what is the correct way to create a JavaScript array?

# a) var items = ["Orange", "Apple"]; ===> Correct Answer

b) var items = {"Orange", "Apple"};

c) var items = new array("Orange", "Apple");

d) var items[] = {"Orange", "Apple"};

# 4)JavaScript: What is the output of the following code
foo = 1;

(function() {

   foo = 2;

})();

var x = function () {

  foo = 3;

};

(function() {

   var foo = 4;

})();

# console.log(foo); // Result : 2

