# `LetterChanges()` with `map()`

```js
function LetterChanges(str) {
  return str
    .split('')
      .map(function(c) {
        if (c.toUpperCase() != c.toLowerCase()) 
          c = String.fromCharCode( c.charCodeAt(0) + 1);
            if (['a', 'e', 'i', 'o', 'u'].indexOf(c) > -1) 
              c = c.toUpperCase();
                return c;
      }).join('');
}
```

`LetterChanges(str)` takes the `str` parameter being passed and modifies it using the following algorithm. *Replace every letter in the string with the letter following it in the alphabet*. Then *capitalize every vowel* in this new string (a, e, i, o, u) and finally return this modified string.

### For Example:

LetterChanges(""hello*3")

*returns* -->
>>>"Ifmmp*3"

___

># Notes and PseudoCode 
* Replace each letter with its neighbor to the right
  - split `str` into an array
  - map over it passing a callback taking `c` as its element argument
    + if the letter is uppercase, make it lowercase
    + re-assign `c` the value of the charcter in the position one greater 
* Find all Vowels and Capitalize Them 
  - determine if letter is a vowel
    + call indexOf() on an array, ['a','e','i','o','u'];
    + if `c` is any of item in this array of vowels,
    + call toUpperCase() on it.
* join() to turn the array created by map() into a string. 

The function contains a return statement, with 3 method calls: `split`, `map`, and `join`.  

This anonymous callback function passed into `map()` does three things with each item in the array before projecting a value into the a new array. 

* Make sure the letter is lowercase
* Assign it the value if the next letter in the alphabet
* If that letter is a vowel, uppercase it. 

```js
    c => {
      if (c.toUpperCase() != c.toLowerCase()) {
        c = String.fromCharCode(c.charCodeAt(0) + 1);
      }
      if (['a', 'e', 'i', 'o', 'u'].indexOf(c) > -1) {
      c = c.toUpperCase();
      }
      return c;
      } )
     
```
Finally, the array `map()` returns is turned back into a string with `join()`

___











