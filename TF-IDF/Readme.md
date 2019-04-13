## Loading Into Pharo

Clone this Repository - git clone <clone with https link>.
This Package was created using the Monticello Browser. To load the package go into the Monticello Browser (Under Tools on topbar or Ctrl+O+P). Press the +repository button and select directory under that. Then find the cloned repository and add that. You will then be able to load the .mcz format packages and use them.

## Functionality
### TF-IDF
TF-IDF stands for “Term Frequency — Inverse Data Frequency”. 
It gives us a metric to evaluate which words are most important in a corpus and which are not.

## Sample Usage for TfIdf Class

``` Pharo
|tf arr1 arr2 corp sol|
tf := TfIdf new.
arr1 := #('The' 'car' 'is' 'driven' 'on' 'the' 'road').
arr2 := #('The' 'truck' 'is' 'driven' 'on' 'the' 'highway').
corp := OrderedCollection new.
corp add: arr1; add: arr2.

tf corpus: corp.
tf build_tfidf
```

## Sample Output

``` Pharo
a Dataframe
```
