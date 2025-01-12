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

# 10. Multi-Film Characters: appearing in more than one film

# Query

```GraphQL
{
  allPeople {
    edges {
      node {
        name
        filmConnection {
          totalCount
        }
      }
    }
  }
}
```

# Response - will need to be filtered to get the ones in more than one film.

```JSON
{
  "data": {
    "allPeople": {
      "edges": [
        {
          "node": {
            "name": "Luke Skywalker",
            "filmConnection": {
              "totalCount": 5
            }
          }
        },
        {
          "node": {
            "name": "C-3PO",
            "filmConnection": {
              "totalCount": 6
            }
          }
        },
        {
          "node": {
            "name": "R2-D2",
            "filmConnection": {
              "totalCount": 7
            }
          }
        },
        {
          "node": {
            "name": "Darth Vader",
            "filmConnection": {
              "totalCount": 4
            }
          }
        },
        {
          "node": {
            "name": "Leia Organa",
            "filmConnection": {
              "totalCount": 5
            }
          }
        },
        {
          "node": {
            "name": "Owen Lars",
            "filmConnection": {
              "totalCount": 3
            }
          }
        },
        {
          "node": {
            "name": "Beru Whitesun lars",
            "filmConnection": {
              "totalCount": 3
            }
          }
        },
        {
          "node": {
            "name": "R5-D4",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Biggs Darklighter",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Obi-Wan Kenobi",
            "filmConnection": {
              "totalCount": 6
            }
          }
        },
        {
          "node": {
            "name": "Anakin Skywalker",
            "filmConnection": {
              "totalCount": 3
            }
          }
        },
        {
          "node": {
            "name": "Wilhuff Tarkin",
            "filmConnection": {
              "totalCount": 2
            }
          }
        },
        {
          "node": {
            "name": "Chewbacca",
            "filmConnection": {
              "totalCount": 5
            }
          }
        },
        {
          "node": {
            "name": "Han Solo",
            "filmConnection": {
              "totalCount": 4
            }
          }
        },
        {
          "node": {
            "name": "Greedo",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Jabba Desilijic Tiure",
            "filmConnection": {
              "totalCount": 3
            }
          }
        },
        {
          "node": {
            "name": "Wedge Antilles",
            "filmConnection": {
              "totalCount": 3
            }
          }
        },
        {
          "node": {
            "name": "Jek Tono Porkins",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Yoda",
            "filmConnection": {
              "totalCount": 5
            }
          }
        },
        {
          "node": {
            "name": "Palpatine",
            "filmConnection": {
              "totalCount": 5
            }
          }
        },
        {
          "node": {
            "name": "Boba Fett",
            "filmConnection": {
              "totalCount": 3
            }
          }
        },
        {
          "node": {
            "name": "IG-88",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Bossk",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Lando Calrissian",
            "filmConnection": {
              "totalCount": 2
            }
          }
        },
        {
          "node": {
            "name": "Lobot",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Ackbar",
            "filmConnection": {
              "totalCount": 2
            }
          }
        },
        {
          "node": {
            "name": "Mon Mothma",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Arvel Crynyd",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Wicket Systri Warrick",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Nien Nunb",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Qui-Gon Jinn",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Nute Gunray",
            "filmConnection": {
              "totalCount": 3
            }
          }
        },
        {
          "node": {
            "name": "Finis Valorum",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Padmé Amidala",
            "filmConnection": {
              "totalCount": 3
            }
          }
        },
        {
          "node": {
            "name": "Jar Jar Binks",
            "filmConnection": {
              "totalCount": 2
            }
          }
        },
        {
          "node": {
            "name": "Roos Tarpals",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Rugor Nass",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Ric Olié",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Watto",
            "filmConnection": {
              "totalCount": 2
            }
          }
        },
        {
          "node": {
            "name": "Sebulba",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Quarsh Panaka",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Shmi Skywalker",
            "filmConnection": {
              "totalCount": 2
            }
          }
        },
        {
          "node": {
            "name": "Darth Maul",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Bib Fortuna",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Ayla Secura",
            "filmConnection": {
              "totalCount": 3
            }
          }
        },
        {
          "node": {
            "name": "Ratts Tyerell",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Dud Bolt",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Gasgano",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Ben Quadinaros",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Mace Windu",
            "filmConnection": {
              "totalCount": 3
            }
          }
        },
        {
          "node": {
            "name": "Ki-Adi-Mundi",
            "filmConnection": {
              "totalCount": 3
            }
          }
        },
        {
          "node": {
            "name": "Kit Fisto",
            "filmConnection": {
              "totalCount": 3
            }
          }
        },
        {
          "node": {
            "name": "Eeth Koth",
            "filmConnection": {
              "totalCount": 2
            }
          }
        },
        {
          "node": {
            "name": "Adi Gallia",
            "filmConnection": {
              "totalCount": 2
            }
          }
        },
        {
          "node": {
            "name": "Saesee Tiin",
            "filmConnection": {
              "totalCount": 2
            }
          }
        },
        {
          "node": {
            "name": "Yarael Poof",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Plo Koon",
            "filmConnection": {
              "totalCount": 3
            }
          }
        },
        {
          "node": {
            "name": "Mas Amedda",
            "filmConnection": {
              "totalCount": 2
            }
          }
        },
        {
          "node": {
            "name": "Gregar Typho",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Cordé",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Cliegg Lars",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Poggle the Lesser",
            "filmConnection": {
              "totalCount": 2
            }
          }
        },
        {
          "node": {
            "name": "Luminara Unduli",
            "filmConnection": {
              "totalCount": 2
            }
          }
        },
        {
          "node": {
            "name": "Barriss Offee",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Dormé",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Dooku",
            "filmConnection": {
              "totalCount": 2
            }
          }
        },
        {
          "node": {
            "name": "Bail Prestor Organa",
            "filmConnection": {
              "totalCount": 2
            }
          }
        },
        {
          "node": {
            "name": "Jango Fett",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Zam Wesell",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Dexter Jettster",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Lama Su",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Taun We",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Jocasta Nu",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "R4-P17",
            "filmConnection": {
              "totalCount": 2
            }
          }
        },
        {
          "node": {
            "name": "Wat Tambor",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "San Hill",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Shaak Ti",
            "filmConnection": {
              "totalCount": 2
            }
          }
        },
        {
          "node": {
            "name": "Grievous",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Tarfful",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Raymus Antilles",
            "filmConnection": {
              "totalCount": 2
            }
          }
        },
        {
          "node": {
            "name": "Sly Moore",
            "filmConnection": {
              "totalCount": 2
            }
          }
        },
        {
          "node": {
            "name": "Tion Medon",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Finn",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Rey",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Poe Dameron",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "BB8",
            "filmConnection": {
              "totalCount": 1
            }
          }
        },
        {
          "node": {
            "name": "Captain Phasma",
            "filmConnection": {
              "totalCount": 1
            }
          }
        }
      ]
    }
  }
}
```

# 11. Aggregate Film Statistics: Calculate the total number of characters across all films.

# Query

```GraphQL
{
  allFilms {
    edges {
      node {
        characterConnection {
          totalCount
        }
      }
    }
  }
}
```

# Response - needs to be summed to get the total numbner of characters across all films.

```JSON
{
  "data": {
    "allFilms": {
      "edges": [
        {
          "node": {
            "characterConnection": {
              "totalCount": 18
            }
          }
        },
        {
          "node": {
            "characterConnection": {
              "totalCount": 16
            }
          }
        },
        {
          "node": {
            "characterConnection": {
              "totalCount": 20
            }
          }
        },
        {
          "node": {
            "characterConnection": {
              "totalCount": 34
            }
          }
        },
        {
          "node": {
            "characterConnection": {
              "totalCount": 40
            }
          }
        },
        {
          "node": {
            "characterConnection": {
              "totalCount": 34
            }
          }
        },
        {
          "node": {
            "characterConnection": {
              "totalCount": 11
            }
          }
        }
      ]
    }
  }
}
```

### Complex Tasks:

# 12. Full Character Profiles: full profile for a given character, including films, starships, and homeworld.

# Query

```GraphQL
{
  person(id:"cGVvcGxlOjEw") {
    name
    birthYear
    homeworld {
      name
    }
    filmConnection {
      films {
        title
      }
    }
    starshipConnection {
      starships {
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
    "person": {
      "name": "Obi-Wan Kenobi",
      "birthYear": "57BBY",
      "homeworld": {
        "name": "Stewjon"
      },
      "filmConnection": {
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
          }
        ]
      },
      "starshipConnection": {
        "starships": [
          {
            "name": "Jedi starfighter"
          },
          {
            "name": "Trade Federation cruiser"
          },
          {
            "name": "Naboo star skiff"
          },
          {
            "name": "Jedi Interceptor"
          },
          {
            "name": "Belbullab-22 starfighter"
          }
        ]
      }
    }
  }
}
```
