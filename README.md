ACTIVITY 1 - John Mark Malapajo

1. Markdown
2. # RESTful API Activity - [John Mark Malapajo]
3. ## Best Practices Implementation
4. **1. Environment Variables:**
5. - Why did we put `BASE_URI` in `.env` instead of hardcoding it?
6. - Answer: We put BASE_URI in the .env file instead of hardcoding it so we can change the API’s base path without editing the source code and this makes the application easier to manage and reduces the chance of errors.
7. **2. Resource Modeling:**
8. - Why did we use plural nouns (e.g., `/dishes`) for our routes?
9. - Answer: We used plural nouns because they represent a collection of resources and follow standard REST API conventions, making the routes clear and consistent.
10. **3. Status Codes:**
11. - When do we use `201 Created` vs `200 OK`?
Answer: We use 201 Created when a new resource is successfully created, such as after a POST request, and 200 OK when a request is successful but does not create a new resource.
12. - Why is it important to return `404` instead of just an empty array or a generic error?
13. - Answer: It is important to return 404 because it clearly tells the client that the requested resource was not found. This makes the API easier to understand, and lets the client handle the error properly.
14.
15. **4. Testing:**
16. - (Paste a screenshot of a successful GET request here)

![alt text](image.png)


--------------------------------------------------------------------------------------------------------------------------
ACTIVITY 3
Deliverable - John Mark Malapajo

1. Why did I choose to Embed the [Review/Tag/Log]?
I chose to embed the Review, Tag, and Log because they are small pieces of data that are directly related to the main document. They do not need to exist on their own and are usually used together with the parent record. Embedding them makes data retrieval faster and keeps related information in one place.

2. "Why did I choose to Reference the [Chef/User/Guest]?
I chose to reference the Chef, User, and Guest because they are separate entities that can exist independently from other records. They may also be connected to multiple documents. Using references helps avoid repeating the same data and keeps the database organized and efficient.




HANDS-ON ACTIVITY 4
Deliverable - John Mark Malapajo

1. What is the difference between Authentication and Authorization in our code?
- Authentication verifies the identity of a user. In our code, this happens when a user logs in by providing their email and password. The system checks the credentials and, if valid, generates a JWT JSON Web Token. Authorization, on the other hand, determines what an authenticated user is allowed to do. After authentication, protected routes check the user's permissions to decide whether the user can access or perform certain actions.

2. Why did we use bcryptjs instead of saving passwords as plain text in MongoDB?
- We use bcryptjs to hash passwords before storing them in the database for security reasons. If passwords were stored as plain text and the database was compromised, attackers would immediately see all user passwords. bcryptjs converts passwords into a secure hash that cannot easily be reversed. When a user logs in, the entered password is hashed again and compared with the stored hash. This ensures that the actual password is never stored or exposed in the database.

3. What does the protect middleware do when it receives a JWT from the client?
- The protect middleware verifies and validates the JWT sent by the client, usually in the Authorization header.