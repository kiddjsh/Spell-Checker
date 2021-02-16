# Spell-Checker
A program that performs a spell check on a string of words and informs the user if they are spelled correctly, and if not, then displays a list of words that could be the correct spelling. The program can handle all the common ways that a word might be a misspelling including:

 - swapping adjacent characters in a word;
 - inserting a single character in between two adjacent characters in a word;
 - deleting a single character from a word; and
 - replacing a character in a word with another character.

A list of correctly spelled words is read from a dictionary file and stored inside a Hash table. The hash table is used to look up words for correct spelling. A spell check function is used to find alternatives for incorrectly spelled words.

# Block Diagram 

![block diagram](https://raw.githubusercontent.com/kiddjsh/Spell-Checker/main/screenshots/blockdiagram.PNG)

# Flowchart 

![flowchart_one](https://raw.githubusercontent.com/kiddjsh/Spell-Checker-Program/main/screenshots/flowchart_one.PNG)
![flowchart_two](https://raw.githubusercontent.com/kiddjsh/Spell-Checker-Program/main/screenshots/flowchart_two.PNG)

# Data Structures Used

A Hash table class is used to store the words from the word dictionary having the following signature where TABLE_SIZE is the hash table initial size.
HashTable<string> hashTable(TABLE_SIZE);
 
A hash table store items by calculating a key index based in the value of the item to be inserted. Collisions  occur when two different items hash to the same index.
The hash table stores a list of nodes corresponding to each index in the hash table.
 
```C++
struct node
{
    ItemType currentItem;
    node* next;
};
```

Each node corresponds to a hash function index into the hash table. Each node stores a link list of words having the same hash index.

# Visualization

![visualization](https://raw.githubusercontent.com/kiddjsh/Spell-Checker-Program/main/screenshots/visualization.PNG)

# Hash index function
In data storage and retrieval applications, use of a hash function is perferable in terms of effiency. Collisions should be infrequent, causing marginal delay, that results in few collisions.

```C++
int HashTable<ItemType>::Hash(ItemType newItem)
{
    long h = 19937;
    std::stringstream convert;

    // convert the parameter to a string using "stringstream"
    convert << newItem;
    std::string temp = convert.str();

    for (unsigned x = 0; x < temp.length(); ++x)
    {
        h = (h << 6) ^ (h >> 26) ^ temp[x];
    }
    return abs(h % hashSize);
}
```

# HashTable UML

![hashtable_uml_one](https://raw.githubusercontent.com/kiddjsh/Spell-Checker-Program/main/screenshots/hashtable_uml_one.PNG)
![hashtable_uml_two](https://raw.githubusercontent.com/kiddjsh/Spell-Checker-Program/main/screenshots/hashtable_uml_two.PNG)

# HashTable Iterator UML

![iterator_uml_one](https://raw.githubusercontent.com/kiddjsh/Spell-Checker-Program/main/screenshots/iterator_uml_one.PNG)
![iterator_uml_two](https://raw.githubusercontent.com/kiddjsh/Spell-Checker-Program/main/screenshots/iterator_uml_two.PNG)


