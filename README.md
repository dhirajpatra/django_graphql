# django graphql with graphene

## this application can be a template for bigger graphql based application for django

## how to install

Clone or download this repository

Run following commands:

`pip install -R requirements.txt`
`python manage.py migrate`
`python manage.py runserver`

Go to the address which came output from above command.

Then you can run the following graphql:

```
query getActors {
  actors {
    id
    name
  }
}
```

```
query getMovie {
  movie(id: 1) {
    id
    title
    actors {
      id
      name
    }
  }
}
```

```
mutation createMovie {
  createMovie(input: {
    title: "Cast Away",
    actors: [
      {
        id: 3
      }
    ]
    year: 1999
  }) {
    ok
    movie{
      id
      title
      actors {
        id
        name
      }
      year
    }
  }
}
```

```
mutation updateMovie {
  updateMovie(id: 2, input: {
    title: "Cast Away",
    actors: [
      {
        id: 3
      }
    ]
    year: 2000
  }) {
    ok
    movie{
      id
      title
      actors {
        id
        name
      }
      year
    }
  }
}
```

```
query getMovies {
  movies{
    id
    title
    actors {
      id
      name
    }
  }
}
```