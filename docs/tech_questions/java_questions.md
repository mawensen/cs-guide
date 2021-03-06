Set vs List vs Map
- List allows duplicates while Set doesn't allow duplicates
- List is an ordered collection, but Set is an unordered collection
- The list allows null elements and you can have many null objects in a List because it also allowed duplicates. Set just allow one null element as there is no duplicate permitted while in Map you can have null values and at most one null key. 

How to choice suitable collection?
- if you want to use Key-Value pair, you can use Map. if you need ordered key-value pair, you can use TreeMap 
if you need to make sure thread safe, you can use ConcurrentHashMap
- If you need to ensure that the elements are unique, you can use Set. 