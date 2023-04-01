# Catalog Service

This application is part of the Polar Bookshop system and provides the functionality for managing
the books in the bookshop catalog. It's part of the project built in the
[Cloud Native Spring in Action](https://www.manning.com/books/cloud-native-spring-in-action) book
by [Thomas Vitale](https://www.thomasvitale.com).

## REST API

|    Endpoint	    |  Method  | Req. body | Status | Resp. body | Description    		   	                     |
|:---------------:|:--------:|:---------:|:------:|:----------:|:------------------------------------------|
|    `/books`     |  `GET`   |           |  200   |   Book[]   | Get all the books in the catalog.         |
|    `/books`     |  `POST`  |   Book    |  201   |    Book    | Add a new book to the catalog.            |
|                 |          |           |  422   |            | A book with the same ISBN already exists. |
| `/books/{isbn}` |  `GET`   |           |  200   |    Book    | Get the book with the given ISBN.         |
|                 |          |           |  404   |            | No book with the given ISBN exists.       |
| `/books/{isbn}` |  `PUT`   |   Book    |  200   |    Book    | Update the book with the given ISBN.      |
|                 |          |           |  201   |    Book    | Create a book with the given ISBN.        |
| `/books/{isbn}` | `DELETE` |           |  204   |            | Delete the book with the given ISBN.      |

## Useful Commands

| Maven Command	                       | Description                                   |
|:-------------------------------------|:----------------------------------------------|
| `./mvnw -DskipTests spring-boot:run` | Run the application.                          |
| `./mvnw -DskipTests package`         | Build the application.                        |
| `./mvnw test`                        | Run tests.                                    |
| `./mvnw -DskipTests package`         | Package the application as a JAR.             |
| `./mvnw ???`                         | Package the application as a container image. |

After building the application, you can also run it from the Java CLI:

```bash
java -jar build/libs/catalog-service-0.0.1-SNAPSHOT.jar
```
