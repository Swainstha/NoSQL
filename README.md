# MongoDB

##### Assignment 1

- The program for assignment 1 is Question1.java.
- It inserts 10000 data into the mongodb database using ramdom number generator.
- Results

		- Time taken with index on id only := 75 ms
		- Time taken with index on firstNumber and secondNumber i.e. firstNumber_1_secondNumber_1 := 43 ms
		- Time taken with index on firstNumber and thirdNumber i.e. firstNumber_1_thirdNumber_1 := 47 ms
		- Time taken with index on thirdNumber i.e. thirdNumber_1 := 12 ms
		- Time taken with index on firstNumber, secondNumber and thirdNumber := 27 ms
		
- Conclusion
			
			The index on thirdNumber i.e. thirdNumber_1 can be used by MongoDB for assisting in query.
			
##### Assignment 2

- The choices listed to improve the speed of inserts were
		
    	1. Add an index on last_name, fist_name if one does not already exist.
    	2. Remove all indexes from the collections, leaving only the index on _id in place.
    	3. Provide a hint to MongoDB that it should not use an index for the inserts.
    	4. Set w=0, =false on writes.
    	5. Build a replica set and insert data into the secondary nodes to free up the primary nodes.
    
- Conclusion

		1. Adding index on last_name and first_name will only reduce the speed of insertions beacuse each index on a collection adds some amount of overhead to the performance of write operations.
		2. Index on id field is default in mongodb.
		3. Inserts don't use indexes.
		4. It will speed up writes but w=0 risk consistency and j=0 risk durability because it tells the system that it does not require acknowledgements from write operations on various machines.
		5. We can't insert data to secondaries, insert/update/delete applies only to primary.


##### Assignment 3

		The answer is 0 i.e. after first document with value "monkey" is added, the document 
		cannot be re inserted because it causes duplicate id error. The duplicate id error comes 
		from the fact that we are trying to insert the same document with same id in the mongo database.
		