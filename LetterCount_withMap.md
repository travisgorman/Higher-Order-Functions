## Letter Count

```js
function LetterCountI(str) {

  var globalMax = 1;
  var answer = -1;
 
  str .split(/\s/)
        .map( word => {
          var max = 0;
            word .split('')
              .map( c => {
                var current = word
                  .match( new RegExp( c, 'g') )
                    .length;
              if ( current > max ) { max = current; }
              });

              if ( max > globalMax ) {
                globalMax = max;
                answer = word;
              }                     
        });

  return answer;

}
```

Take the `str` parameter being passed and return the first word with the greatest number of repeated letters. If there are no words with repeated letters return -1

```js
LetterCountI("alls I ever eats is roosbeeeef");
```

*returns* -->
>>>"roosbeeeef"

___
