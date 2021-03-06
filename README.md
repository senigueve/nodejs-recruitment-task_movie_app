# Movie API 

## Technology stack

As the name suggests, this repository is built on top of Node.js and Express.js and MongoDB

#### Server side

- Node.js - evented I/O for the backend

- Express.js - Express.js is an automatically prebuilt Node.js framework that facilitates us to create server-side web applications faster and smarter. The main reason   for choosing Express is its simplicity, minimalism, flexibility, and scalability characteristics.

- MongoDB -  the most popular NoSQL system, especially among startups. A document-oriented database with JSON-like documents in dynamic schemas.

- Mongoose - mongoose

- Jest - JavaScript testing framework

- Super Test - Super test API testing framework


## Run locally

1. Clone this repository
1. Go to movie folder and run docker-compose command


By default the auth service will start on port `3003`. You can run the application using docker. 

```
docker-compose up -d
```

To stop the authorization service run

```
docker-compose down
```

## API Endpoint Request/Response
To authorize user call the movie service using for example `curl`. We assume
that the movie service is running of the default port `3003`.


#### POSTE movie
Request

```
curl --location --request POST '0.0.0.0:3003/movies' \
--header 'Content-Type: application/json' \
--data-raw '{
    "title": "titanic",
}'
```

Response

```
{
    "userId": 123,
    "_id": "62341281c575566a846854f5",
    "title": "Titanic",
    "released": "1997-12-18T18:00:00.000Z",
    "genre": "Drama, Romance",
    "director": "James Cameron",
    "__v": 0
}
```

#### GET movie
Request

```
curl --location --request GET '0.0.0.0:3003/movies' \
--header 'Content-Type: application/json' \
--data-raw '{
    "title": "titanic",
}'
```

Response

```
[
    {
        "userId": 123,
        "_id": "62341281c575566a846854f5",
        "title": "Titanic",
        "released": "1997-12-18T18:00:00.000Z",
        "genre": "Drama, Romance",
        "director": "James Cameron",
        "__v": 0
    }
]
```
