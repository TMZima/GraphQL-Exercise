# 1. List All films

### Query

```GraphQL
{
  allFilms {
    films {
      title
    }
  }
}
```

### Response

```JSON
{
  "data": {
    "allFilms": {
      "films": [
        {
          "title": "A New Hope"
        },
        {
          "title": "The Empire Strikes Back"
        },
        {
          "title": "Return of the Jedi"
        },
        {
          "title": "The Phantom Menace"
        },
        {
          "title": "Attack of the Clones"
        },
        {
          "title": "Revenge of the Sith"
        },
        {
          "title": "The Force Awakens"
        }
      ]
    }
  }
}
```

# 2. Fetch a Specific Character

# Query

```GraphQL
{
  person (id:"cGVvcGxlOjM="){
    name
  }
}
```

# Response

```JSON
{
  "data": {
    "person": {
      "name": "R2-D2"
    }
  }
}
```

# 3. Explore Planets - First 5 planets

# Query

```GraphQL
{
  allPlanets(first:5) {
    planets {
      name
    }
  }
}
```

# Response

```JSON
{
  "data": {
    "allPlanets": {
      "planets": [
        {
          "name": "Tatooine"
        },
        {
          "name": "Alderaan"
        },
        {
          "name": "Yavin IV"
        },
        {
          "name": "Hoth"
        },
        {
          "name": "Dagobah"
        }
      ]
    }
  }
}
```
