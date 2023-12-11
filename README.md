# Chat
Implementation of key mechanisms to work with PostgreSQL DBMS via JDBC

In this chat, user can create or choose an existing chatroom. 
Each chatroom can have several users exchanging messages.

**ex00**

Key domain models which both SQL tables and Java classes implemented for are:
User:
- User ID
- Login
- Password
- List of created rooms
- List of chatrooms where a user socializes

Chatroom:
- Chatroom id
- Chatroom name
- Chatroom owner
- List of messages in a chatroom

Message:
- Message id
- Message author
- Message room
- Message text
- Message date/time

**ex01**
- Implemented MessagesRepository with a SINGLE Optional<Message> findById(Long id) method and its MessagesRepositoryJdbcImpl implementation.
- This method return a Message object where author and chatroom specified.  
- The implemented code tested in Program.java class.

**ex02**
- Implemented save(Message message) method for MessagesRepository.
-   Defined the subentities for the entity we are saving—a message author and a chatroom. 
- Assigned IDs that exist in the database to chatroom and author.

**ex03**
- Implemented update method in MessageRepository.
- This method fully update an existing entity in the database. 

**ex04**
- Implemented UsersRepository interface and UsersRepositoryJdbcImpl class using a SINGLE List<User> findAll(int page, int size) method.
- This method return size—users shown in the page with page number. 
- In this task, each user in the resulting list had included dependencies—a list of chatrooms created by that user, as well as a list of chatrooms the user participates in.
- Each subentity of the user not include its dependencies, i.e. list of messages inside each room must be empty.
- The implemented method operation demonstrated in Program.java.
