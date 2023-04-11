## Why hashamp lookup is O(1) constant time
- Hashmap lookup is O(1) amortized
- This is because we have a load factor, which is a threshold that whenever achieved according to size of hash table, we would increase the size of hashtable
- If our load factor is 50%, and our hash table is of size 100 and we already have 50 elements, we would rebuilt the internal bucket structure, such as rehashing the values while increasing the hash table size, which introduces a performance penalty of likely O(N)
- Good practice is the hash table will have approximately twice the number of buckets