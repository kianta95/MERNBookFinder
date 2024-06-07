# MERNBookFinder

This project is a full-stack application that implements a book search engine. It utilizes the MERN stack (MongoDB, Express.js, React.js, Node.js) along with GraphQL for API queries and mutations.

Back-End Tasks
auth.js

Update the auth middleware function to work with the GraphQL API.
server.js

Implement the Apollo Server and apply it to the Express server as middleware.
Schemas Directory

index.js
Export your typeDefs and resolvers.
resolvers.js
Define the query and mutation functionality to work with the Mongoose models.
Hints

typeDefs.js: Define the necessary Query and Mutation types.

Query type:
me: Returns a User type.

Mutation type:

login: Accepts an email and password as parameters; returns an Auth type.

addUser: Accepts a username, email, and password as parameters; returns an Auth type.

saveBook: Accepts a book author's array, description, title, bookId, image, and link as parameters; returns a User type. (Consider creating an input type to handle these parameters.)

removeBook: Accepts a book's bookId as a parameter; returns a User type.


User type:
_id
username
email
bookCount
savedBooks (An array of Book type.)
Book type:
bookId
authors
description
title
image
link
Auth type:
token
user (References the User type.)
Front-End Specifications
Front-End Files

queries.js: Holds the query GET_ME, which executes the me query set up using Apollo Server.
mutations.js:
LOGIN_USER executes the loginUser mutation set up using Apollo Server.
ADD_USER executes the addUser mutation.
SAVE_BOOK executes the saveBook mutation.
REMOVE_BOOK executes the removeBook mutation.


Additional Front-End Tasks

App.jsx: Creates an Apollo Provider to make every request work with the Apollo server.
SearchBooks.jsx:
Utilizes the Apollo useMutation() Hook to execute the SAVE_BOOK mutation in the handleSaveBook() function.
Ensures logic for saving the book's ID to state is kept in the try...catch block.
SavedBooks.jsx:
Removes the useEffect() Hook that sets the state for UserData.
Utilizes the Apollo useQuery() Hook to execute the GET_ME query on load and saves it to a variable named userData.
Utilizes the Apollo useMutation() Hook to execute the REMOVE_BOOK mutation in the handleDeleteBook() function.
SignupForm.jsx: Replaces the addUser() functionality with the ADD_USER mutation functionality.
LoginForm.jsx: Replaces the loginUser() functionality with the LOGIN_USER mutation functionality.