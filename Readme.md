## Loading Into Pharo

Clone this Repository - git clone <clone with https link>.
This Package was created using the Monticello Browser. To load the package go into the Monticello Browser (Under Tools on topbar or Ctrl+O+P). Press the +repository button and select directory under that. Then find the cloned repository and add that. You will then be able to load the .mcz format packages and use them.

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
Number of tokens - 23140

``` Pharo
ngrams := Ngrams new.
ngrams tokens: arr.
ngrams nvalue: 5.
[ ngrams get_ngrams. ] timeToRun 
```
``` Pharo
Runtime - 00.002 Seconds
```

Comparing with generation using NLTK python

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

Comparing with generation using pure python (zip function)
``` Python
def generate_ngrams(tokens, n):    
    ngrams = zip(*[tokens[i:] for i in range(n)])
    return [" ".join(ngram) for ngram in ngrams]
```

``` Python
Runtime - 0.012454032897949219 Seconds
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
