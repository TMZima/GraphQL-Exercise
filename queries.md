#### Basic Tasks:

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

# 4. Starships Information: Names and models of 3 starships

# Query

```GraphQL
{
  allStarships (last: 3){
    starships {
      name
      model
    }
  }
}
```

# Response

```JSON
{
  "data": {
    "allStarships": {
      "starships": [
        {
          "name": "Belbullab-22 starfighter",
          "model": "Belbullab-22 starfighter"
        },
        {
          "name": "V-wing",
          "model": "Alpha-3 Nimbus-class V-wing starfighter"
        },
        {
          "name": "T-70 X-wing fighter",
          "model": "T-70 X-wing fighter"
        }
      ]
    }
  }
}
```

### Intermediate Tasks:

# 5. Character and Their Starships - For each of the first 5 characters, list the names of starships they've piloted.

# Query

```GraphQL
{
  allPeople(first:5){
    edges{
      node {
        name
        starshipConnection{
          starships {
            name
          }
        }
      }
    }
  }
}
```

# Response

```JSON
{
  "data": {
    "allPeople": {
      "edges": [
        {
          "node": {
            "name": "Luke Skywalker",
            "starshipConnection": {
              "starships": [
                {
                  "name": "X-wing"
                },
                {
                  "name": "Imperial shuttle"
                }
              ]
            }
          }
        },
        {
          "node": {
            "name": "C-3PO",
            "starshipConnection": {
              "starships": []
            }
          }
        },
        {
          "node": {
            "name": "R2-D2",
            "starshipConnection": {
              "starships": []
            }
          }
        },
        {
          "node": {
            "name": "Darth Vader",
            "starshipConnection": {
              "starships": [
                {
                  "name": "TIE Advanced x1"
                }
              ]
            }
          }
        },
        {
          "node": {
            "name": "Leia Organa",
            "starshipConnection": {
              "starships": []
            }
          }
        }
      ]
    }
  }
}
```

# 6. Species and Their Languages: Names and languages of 5 species

# Query

```GraphQL
{
 allSpecies(last:5){
  edges {
		node {
    	name
    	language
  		}
 		}
	}
}
```

# Response

```JSON
{
  "data": {
    "allSpecies": {
      "edges": [
        {
          "node": {
            "name": "Skakoan",
            "language": "Skakoan"
          }
        },
        {
          "node": {
            "name": "Muun",
            "language": "Muun"
          }
        },
        {
          "node": {
            "name": "Togruta",
            "language": "Togruti"
          }
        },
        {
          "node": {
            "name": "Kaleesh",
            "language": "Kaleesh"
          }
        },
        {
          "node": {
            "name": "Pau'an",
            "language": "Utapese"
          }
        }
      ]
    }
  }
}
```

# 7. Planets and Their Climates: 5 planets

# Query

```GraphQL
{
 allPlanets(first:5) {
  planets {
    name
    climates
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
          "name": "Tatooine",
          "climates": [
            "arid"
          ]
        },
        {
          "name": "Alderaan",
          "climates": [
            "temperate"
          ]
        },
        {
          "name": "Yavin IV",
          "climates": [
            "temperate",
            "tropical"
          ]
        },
        {
          "name": "Hoth",
          "climates": [
            "frozen"
          ]
        },
        {
          "name": "Dagobah",
          "climates": [
            "murky"
          ]
        }
      ]
    }
  }
}
```

# 8. Vehicles and Their Costs: names and cost in credits for 3 vehicles

# Query

```GraphQL
{
 allVehicles(first:3){
  vehicles{
    name
    costInCredits
  	}
	}
}
```

# Response

```JSON
{
  "data": {
    "allVehicles": {
      "vehicles": [
        {
          "name": "Sand Crawler",
          "costInCredits": 150000
        },
        {
          "name": "T-16 skyhopper",
          "costInCredits": 14500
        },
        {
          "name": "X-34 landspeeder",
          "costInCredits": 10550
        }
      ]
    }
  }
}
```

### Advanced Tasks:

# 9. Characters in a Specific Film: List all characters appearing in a given film by ID.

# Query

```GraphQL
{
  film(id:"ZmlsbXM6NA==") {
    characterConnection {
      characters {
        name
      }
    }
  }
}
```

# Response

```JSON
{
  "data": {
    "film": {
      "characterConnection": {
        "characters": [
          {
            "name": "C-3PO"
          },
          {
            "name": "R2-D2"
          },
          {
            "name": "Obi-Wan Kenobi"
          },
          {
            "name": "Anakin Skywalker"
          },
          {
            "name": "Jabba Desilijic Tiure"
          },
          {
            "name": "Yoda"
          },
          {
            "name": "Palpatine"
          },
          {
            "name": "Qui-Gon Jinn"
          },
          {
            "name": "Nute Gunray"
          },
          {
            "name": "Finis Valorum"
          },
          {
            "name": "Padmé Amidala"
          },
          {
            "name": "Jar Jar Binks"
          },
          {
            "name": "Roos Tarpals"
          },
          {
            "name": "Rugor Nass"
          },
          {
            "name": "Ric Olié"
          },
          {
            "name": "Watto"
          },
          {
            "name": "Sebulba"
          },
          {
            "name": "Quarsh Panaka"
          },
          {
            "name": "Shmi Skywalker"
          },
          {
            "name": "Darth Maul"
          },
          {
            "name": "Ayla Secura"
          },
          {
            "name": "Ratts Tyerell"
          },
          {
            "name": "Dud Bolt"
          },
          {
            "name": "Gasgano"
          },
          {
            "name": "Ben Quadinaros"
          },
          {
            "name": "Mace Windu"
          },
          {
            "name": "Ki-Adi-Mundi"
          },
          {
            "name": "Kit Fisto"
          },
          {
            "name": "Eeth Koth"
          },
          {
            "name": "Adi Gallia"
          },
          {
            "name": "Saesee Tiin"
          },
          {
            "name": "Yarael Poof"
          },
          {
            "name": "Plo Koon"
          },
          {
            "name": "Mas Amedda"
          }
        ]
      }
    }
  }
}
```
