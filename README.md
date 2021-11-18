# BookstoreAPIServer

A simple api server which can be used as backend of a e-bookstore. User can get list of books and authors. Details of a book can be found using GET method by passing book name or ISBN as parameter. Details about authors can be found using GET method by passing author name as parameter. After registration and login, User can Add/Update and Delete books from the server

## Running the server
After changing the directory to project directory
`go run .`

## performing api tasks

|method|url|body|actions|
|---|---|---|---|
|POST|`http://localhost:8081/register`|{"username": "shaad","password":"1234"}| Register new user|
|POST|`http://localhost:8081/login`|{"username": "shaad","password":"1234"} | Loggin In the user|
|POST|`http://localhost:8080/logout`||Logging Out|
|GET|`http://localhost:8081/books`||Returns Details of all books|
|GET|`http://localhost:8081/books/simple`||Return list of books name|
|GET|`http://localhost:8081/books/isbn/{ISBN}`||Returns Details of the Book of the given ISBN|
|GET|`http://localhost:8081/books/name{BookName}`||Return Details of the given book name|
|GET|`http://localhost:8081/authors`||Return list of authors|
|GET|`http://localhost:8081/authors/{AuthorName}`||Returns Details of the given author|
|DELETE|`http://localhost:8081/books/{ISBN`||Delete the book entry matching ISBN|
-----------------

And UPDATE and ADD methods can be called in the url `http://localhost:8081/books` with a request body which contains the details of the books in following format. To update a book info the isbn of the book should be passed as URL parameter. 
```
{
    "book_name" : "The Sicilian",
    "author_info" : {
        "name" : "Mario Puzo",
        "date_of_birth" : "October 15, 1920",
        "birth_place" : "United States"
    },
    "ISBN" : "0-671-43564-7",
    "Genre" : "Thriller",
    "Publisher" : "Random House"
}
```



