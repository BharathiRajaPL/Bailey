# Bailey



Write a multiplication function in javascript to use like this.

function mul(x) {
return function (y) {
return function (z) {
return x*y*z;
}
}
}
console.log(mul(2)(3)(4));
