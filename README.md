# Bailey



#1)Write a multiplication function in javascript to use like this.

function mul(x) {
return function (y) {
return function (z) {
return x*y*z;
}
}
}
console.log(mul(2)(3)(4));

#2)Which of the following code snippet append an element value at the end of the array, arr?

a) arr[arr.length+1] = value

#b) arr[arr.length] = value===> Correct Answer

c) arr[arr.length - 1] = value

d) arr = arr + value 
