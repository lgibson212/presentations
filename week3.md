# Explain and provide an example of the average case and worst case time complexity for insertion and deletion in a hash table.

an associative array... a python dictionary is a hash table.

Key:Value pairs

Thus, it becomes a data structure in which insertion and search operations are very fast irrespective of the size of the data. Hash Table uses an array as a storage medium and uses hash technique to generate an index where an element is to be inserted or is to be located from.

Hashing is a technique to convert a range of key values into a range of indexes of an array. (It usually involves a modulo function)

This allows us to search for key values in constant, O(1), time. We simply use the hash function to compute the slot name for the item and then check the hash table to see if it is present. A constant amount of time is required to compute the hash value and then index the hash table at that location. If everything is where it should be, we have found a constant time search algorithm.

However, due to collisions, instances where the hashing technique did not result in a unique location and wants to put an item in a location that is already occupied, a search for a location would take longer and depends on the probing method used. Some hashing techniques use a linear search function to find the next empty, some use chaining. Both would mean the search would take closer to O(n) time.

If the hash table does not have a fixed size but can shrink and grow as more keys are added and deleted, then every now and then the hash table needs to be resized, which takes a lot of time. So in those cases, insertion and deletion can sometimes take very long. This would be the worst case scenario. Although on average the time complexity is still O(1)- this is called amortized O(1).
 
 
Insert
Whenever an element is to be inserted, compute the hash code of the key passed and locate the index using that hash code as an index in the array. If an element is found at the computed hash code, use a method to find an empty location. linear probing for example.

Delete
Whenever an element is to be deleted, compute the hash code of the key passed and locate the index using that hash code as an index in the array. Use linear probing to get the element ahead if an element is not found at the computed hash code. When found, store a dummy item there to keep the performance of the hash table intact.


Also does not take into account the hashing technique time- the function would most probably have a complexity of its own

- https://www.tutorialspoint.com/data_structures_algorithms/hash_data_structure.htm
- http://interactivepython.org/runestone/static/pythonds/SortSearch/Hashing.html



Question: Why is this faster than referring to an object by its direct memory location?
Why bother hashing and putting it into a hash table?

Memory Address as Hash in HashTable. Why can't HashTable use actual memory address of the Key as Hash?
