## Sample Usage for Ngrams Class

``` Pharo
|arr ngrams|
arr := #('this' 'is' 'a' 'test').

ngrams := Ngrams new.
ngrams tokens: arr.
ngrams nvalue: 2.
ngrams get_ngrams
```

## Sample Output

``` Pharo
"an OrderedCollection(#('this' 'is') #('is' 'a') #('a' 'test'))"
```
