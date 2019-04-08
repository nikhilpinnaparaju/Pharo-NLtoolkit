## Loading Into Pharo

Clone this Repository - git clone <clone with https link>.
This Package was created using the Monticello Browser. To load the package go into the Monticello Browser (Under Tools on topbar or Ctrl+O+P). Press the +repository button and select directory under that. Then find the cloned repository and add that. You will then be able to load the .mcz format packages and use them.

## Functionality
### Linked Lists
A linked list is a linear data structure where each element is a separate object. Linked list elements are not stored at contiguous location; the elements are linked using pointers. Each node of a list is made up of two items - the data and a reference to the next node. The last node has a reference to null.

## Sample Usage for Ngrams Class
Inspecting this using the inspector allows us to look into the class and what is happening properly.

``` Pharo
| slist node1 node2 node3 xl|

node1 := BasicLink new.
node1 value: 2.

node2 := BasicLink new.
node2 value: 4.

node3 := BasicLink new.
node3 value: 4.

slist := BasicLinkedList new.
slist add: node1.

slist.

slist add: node2.
slist asArray .

slist add: node3.
slist asArray .
```

## Samplel size.

``` Pharol size.
"an OrderedCollection(2 4 4)"
```

## Classes and Methods
### Class BasicLink
This is the linked list's link class that holds the value and the pointer to the nextnode.

#### Methods in BasicLink
nextlink - return the nextnode <br>
nextlink: - set nextnode <br>
value - return the nodes value <br>
value: - set nodes value <br>
clearLinks - remove reference to nextnode <br>

### Class BasicLinkedList
This is the linked list class.

#### Methods in BasicLinkedList
add: - add node to linkedlist <br>
addLast: - add node to end of linkedlist <br>
asArray - return linkedlist as an orderedCollection <br>
first - return first element on linkedlist <br>
isEmpty - check if linkedlist is empty <br>
removeAll - empty the linkedlist <br>