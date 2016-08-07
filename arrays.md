###Splice
The **splice()** method changes the contents of an array by removing existing elements and/or adding new elements to the array. This method modifies the original array.
```
var food = ['spinach','bacon','chicken','fish','potatoes'];
var favFood = food.splice(1,3,"brinjal");
//favFood = ["bacon","chicken","fish"]
//food = ["spinach","brinjal","potatoes"]
```
_If you don't specify any items to add, **splice()** will only delete the items from the array_

**Return Value**
An array containing the removed elements. If only one element is removed, an array of one element is returned. If no element is removed, it returns an empty array.
***
###Slice

The **slice()** method returns a shallow copy of array into a new array object. The original array is not modified.

```
var food = ['spinach','bacon','chicken','fish','potatoes'];
var favFood = food.slice(1,4);
//favFood = ["bacon", "chicken", "fish"]
```
**Return Value**
A new array containing the extracted elements.
***
###Pop,Push, Shift, UnShift

The **pop()** method removes the last element from the array and returns that element.

The **push()** method adds one or more elements to the end of array and returns the length of the array.

The **shift()** method removes the first element from the array and returns that element.

The **unshift()** method adds one or more elements to the start of the array and returns the length of the array.
***
###Filter
The **filter()** method creates a new array with all the elements that pass the test implemented by the provided function.

_filter()_ calls the provided callback function once for every element of the array, and constructs a new array with all elements for which the callback returns true.

**Return Value**
A new array with elements that pass the test. The return value from the _filter_ callback should be boolean, indicating whether to include the original value in the result(true) or whether to leave it out (false). You can't return the value itself, just a boolean - you can't modify the value from within the callback.

```
var numbers = [1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20];
function getEven(num){
  return num % 2 == 0;
}
var evenNumbers = numbers.filter(getEven);
//evenNumbers = [2, 4, 6, 8, 10, 12, 14, 16, 18, 20]
```
***
###Map
The **map()** method creates a new array with the results of calling the provided function on every element in the array. Think of **_map_** as a for-each loop, that is specifically for transforming values - one input value corresponds to one _'transformed'_ output value.

For the **map()** method, the amount of input elements is equal to the amount of output elements. 

**Return Value**
A new array

```
var numbers = [1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20];
var squares = numbers.map(function(num){
  return num * num;
});
/squares = [1, 4, 9, 16, 25, 36, 49, 64, 81, 100, 121, 144, 169, 196, 225, 256, 289, 324, 361, 400]
```
_**Map & Filter Chained**_
* For a numbers array, double the odd numbers but throw away the even numbers
```
var numbers = [1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20];
var doubledOdds = numbers.filter(function(num){ 
  return num % 2 !== 0;
}).map(function(num){
  return num * 2;
});
//doubledOdds = [2, 6, 10, 14, 18, 22, 26, 30, 34, 38];
```
***
###Reduce
The **reduce()** method applies a function against an accumulator and each value of the array to reduce it to a single value.

**Return Value**
**reduce()** always returns just the total value - unless you have specifically made it an array, it won't be like an array for _map_ and _filter_.

* add the even numbers to the resulting array twice, but the odd numbers only once.
```
var numbers = [1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20];
var newNumbers = numbers.reduce(function(newArray, num){
  newArray.push(num);
  if(num % 2 == 0){
    newArray.push(num);  
  }
  return newArray;
}, []);
//newNumbers = [1, 2, 2, 3, 4, 4, 5, 6, 6, 7, 8, 8, 9, 10, 10, 11, 12, 12, 13, 14, 14, 15, 16, 16, 17, 18, 18, 19, 20, 20]
```
