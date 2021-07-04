## JavaScript Array methods

In javaScript everything was object, so the array it has a inbuilt methods to work on the array elements.

**important**

```
[].constructor

```

every object in javaScript has a constructor property, this property returns the function which used to create the object. In the above example the answer will be `function Array()` this function is used to create an array object in hood. So function are used to create an object in the javascript, the new class syntax do the same under the hood, and every functions are object.

#### concat method

The concat() method is used to merge two or more arrays. a method follow a functional programming approach, it does not alter the existing arrays, it will returns a new array with combining given parameter, if no parameter is provided then the method will return the same array as new array.

```

const array1 = [1, 2, 3];
const array2 = ["a", "b", "c"];

const newArray = array1.concat(array2);

console.log(newArray); // => [1, 2, 3, "a", "b", "c"]

```

> concat copies the object refrence into the new array, if the new array is modified then the original array will also be overwritten. where as primitives are copied as value.

> return new array

#### copyWithin

copy the part of an array elements from existing location to new location in the same array and modify the orginal array.

#####syntax
[].copyWithin(target, start, end);

```
const array = [1, 2, 3, 4, 5, 6];

console.log(array.copyWithin(0, 3, 4)); // [4, 2, 3, 4, 5, 6]

```

> returns orgianl array with modified

#### entries

This method returns an array iterator object, with key and value pair, index as key and elements as value.

```
const a = ['a', 'b', 'c'];

for (const [index, element] of a.entries())
  console.log(index, element);

// 0 'a'
// 1 'b'
// 2 'c'

```

> returns an Array iterator object.

### every

this method test on `every` elements of an array if all passed the test then it will return true else false on occurance of first false statement

_syntax_
[].every(element, index, arry) // if arrow function used.

[].every(callback, thisArg) // if callback function used.

[].every(function callback(element, index, arry), thisArg) // if inline callback function used.())

arrow function example.

```
[1, 2, 3].every((element) => element>2) // return false.
[1, 2, 3].every((element) => element>=1) // return true.

```

callback function example.

```

functon chaeck(element, index, arry){
    return element>2;
}

[1, 2, 3].every(chaeck);

```

> return boolean value, not affect the original array.

#### fill

this method return a modified array with replaced elements so the name fill, it's static operation means changes the value without considering anything.

_syntax_
[].fill(value, start, end);

example.

```
[1, 2, 3].fill(8, 1); // [1, 8, 8]

```

> return a old modified array.

#### filter

this method filter all elements of the array and return new array with the elements who passed the filter function.

_syntax_

[].filter(element, index, array); // if arrow function used.

[].filter(callback, thisArg) // if callback function used.

[].filter(function callback(element, index, arry), thisArg) // if inline callback function used.())

example.

```
[1, 2, 3, 4, 5, 6].filter((element)=> element%2 == 0); // [2,4,6];

```

```
// from mdn site

const array = [-3, -2, -1, 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13];

function isPrime(num) {
  for (let i = 2; num > i; i++) {
    if (num % i == 0) {
      return false;
    }
  }
  return num > 1;
}

console.log(array.filter(isPrime)); // [2, 3, 5, 7, 11, 13]

```
