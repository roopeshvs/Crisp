# Crisp

A URL Shortener service created using Python, Django and GraphQL.

### Why Crisp?

This is a learning project to learn about Queries and Mutations in GraphQL and about Hashing Algorithms.

## Running Crisp Locally

### Cloning the Repository

Clone this repository by running the command

`git clone https://github.com/roopeshvs/Crisp.git`

For Linux, use
`python3 -m venv VENV`

For Windows, use
`python -m venv VENV`

### Activating A Python Virtual Environment

For Linux Bash, use
`VENV/bin/activate`

For Windows Command Prompt, use
`VENV\Scripts\activate.bat`

### Installing Dependencies

Install the required dependencies by running the command
`pip install -r requirements.txt`

### Setting Up The Database

To create tables in your database, run the commands

For Linux, use

`python3 manage.py makemigrations`

`python3 manage.py migrate`

For Windows, use

`python manage.py makemigrations`

`python manage.py migrate`

### You Are All Set!

To start the server, run the command

For Linux, use

`python3 manage.py runserver`

For Windows, use

`python manage.py runserver`

### GraphiQL Interface

Head over to http://localhost:8000/graphql/ to visit the beautiful interface provided by GraphiQL.

## Using Crisp through GraphiQL

### Shortening A URL

Replace all the contents on the left pane with the following mutation.

```javascript
mutation {
  createUrl(fullUrl:"https://github.com/roopeshvs/Crisp") {
    url {
      id
      fullUrl
      urlHash
      clicks
      createdAt
    }
  }
}
```

You can see your URL Hash at the Right Pane in the GraphiQL interface.

You can now visit the original URL at http://localhost:8000/{urlHash}

Note that only valid URLs will generate an Output.

### List of All Shortened URLs

Get the list of all your shortened URLs using the following query.

```javascript
query {
  urls {
    id
    fullUrl
    urlHash
    clicks
    createdAt
  }
}
```

### Filtered List of Shortened URLs

Get a Filtered List of your shortened URLs using the following query.

```javascript
query {
  urls(url:"Crisp") {
    id
    fullUrl
    urlHash
    clicks
    createdAt
  }
}
```

### Paginated List of Shortened URLs

Get a Paginated List of your shortened URLs using the following query.

```javascript
query {
  urls(first: 2, skip: 1) {
    id
    fullUrl
    urlHash
    clicks
    createdAt
  }
}
```

## To-Do

* Integrate With A Front-End.
* Implement Production-Ready Collision, Hashing Functions & Bloom Filter.
* Add User Authentication and OAuth.