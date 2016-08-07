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
A new array with elements that pass the test

```
var numbers = [1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20];
function getEven(num){
  return num % 2 == 0;
}
var evenNumbers = numbers.filter(getEven);
//evenNumbers = [2, 4, 6, 8, 10, 12, 14, 16, 18, 20]
```
