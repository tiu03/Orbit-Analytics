# Why MongoDB
- **NoSQL** database learned in uni before flexible 
- difference formats   binary JSON-like structure can store varied data s documents, adding new fields without the complex schema migrations, so it eliminates schema migration bottleneck evolve with data 


The principle "data access together should be stored together" "helps you design efficient schemas. 
	- Embed data when you need atomic operations and fast reads
	- When optimizing for different access patterns or managing large datasets, use references to other collection

Database failures - to address MongoDB use replica sets (groups of servers that maintain identical copies of your data) 
	 - MongoDB automatically promotes a secondary node with no manual intervention and minimal downtime.






---
[from geeks for geeks course](https://www.geeksforgeeks.org/courses/category/mongodb)  
  