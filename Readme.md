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

## Benchmarking and Comparing with Python

Putting the Gutenberg Corpus into **arr** and comparing NLTK (Python) N-gram speed and my implementation.

``` Pharo
ngrams := Ngrams new.
ngrams tokens: arr.
ngrams nvalue: 5.
[ ngrams get_ngrams. ] timeToRun 
```
``` Pharo
Runtime - 00.002 Seconds
```

``` Python
tokens = gutenberg.words('shakespeare-macbeth.txt')
start = time.time()
output = list(ngrams(tokens, 5))
end = time.time()
runtime = end - start
```
``` Python
Runtime - 0.054718017578125 Seconds
```
Generation of **arr** was done using python as I was unable to load the tokenized gutenberg corpus in Pharo.
``` Python
s = '#('
for token in tokens:
    if token != '\'':
        s += '\'' + token.lower() + '\'' + ' '
s += ').'
f = open('gutenberg.txt','w+')
f.write(s)
f.close()
```
