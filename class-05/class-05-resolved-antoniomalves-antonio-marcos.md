# MongoDB - Aula 05 - Exercicio
autor: Antonio Marcos Alves

## Importar as collections restaurantes e pokemons- passo 01

'''
mongoimport --db be-mean --collection restaurantes --drop --file ~/Documentos/projetos/projetos_javascript/curso-beMEAN/restaurantes.json 
2015-11-28T22:42:48.650-0200	connected to: localhost
2015-11-28T22:42:48.651-0200	dropping: be-mean.restaurantes
2015-11-28T22:42:51.352-0200	imported 25359 documents


mongoimport --db be-mean --collection restaurantes --drop --file ~/Documentos/projetos/projetos_javascript/curso-beMEAN/restaurantes.json 
2015-11-28T22:42:48.650-0200	connected to: localhost
2015-11-28T22:42:48.651-0200	dropping: be-mean.restaurantes
2015-11-28T22:42:51.352-0200	imported 25359 documents
'''

## Distinct por 'cuisine' na restaurantes - passo 02
db.restaurantes.distinct('cuisine').sort()

[
  "Afghan",
  "African",
  "American ",
  "Armenian",
  "Asian",
  "Australian",
  "Bagels/Pretzels",
  "Bakery",
  "Bangladeshi",
  "Barbecue",
  "Bottled beverages, including water, sodas, juices, etc.",
  "Brazilian",
  "CafÃ©/Coffee/Tea",
  "Café/Coffee/Tea",
  "Cajun",
  "Californian",
  "Caribbean",
  "Chicken",
  "Chilean",
  "Chinese",
  "Chinese/Cuban",
  "Chinese/Japanese",
  "Continental",
  "Creole",
  "Creole/Cajun",
  "Czech",
  "Delicatessen",
  "Donuts",
  "Eastern European",
  "Egyptian",
  "English",
  "Ethiopian",
  "Filipino",
  "French",
  "Fruits/Vegetables",
  "German",
  "Greek",
  "Hamburgers",
  "Hawaiian",
  "Hotdogs",
  "Hotdogs/Pretzels",
  "Ice Cream, Gelato, Yogurt, Ices",
  "Indian",
  "Indonesian",
  "Iranian",
  "Irish",
  "Italian",
  "Japanese",
  "Jewish/Kosher",
  "Juice, Smoothies, Fruit Salads",
  "Korean",
  "Latin (Cuban, Dominican, Puerto Rican, South & Central American)",
  "Mediterranean",
  "Mexican",
  "Middle Eastern",
  "Moroccan",
  "Not Listed/Not Applicable",
  "Nuts/Confectionary",
  "Other",
  "Pakistani",
  "Pancakes/Waffles",
  "Peruvian",
  "Pizza",
  "Pizza/Italian",
  "Polish",
  "Polynesian",
  "Portuguese",
  "Russian",
  "Salads",
  "Sandwiches",
  "Sandwiches/Salads/Mixed Buffet",
  "Scandinavian",
  "Seafood",
  "Soul Food",
  "Soups",
  "Soups & Sandwiches",
  "Southwestern",
  "Spanish",
  "Steak",
  "Tapas",
  "Tex-Mex",
  "Thai",
  "Turkish",
  "Vegetarian",
  "Vietnamese/Cambodian/Malaysia"
]
'''

## Distinct por 'types' na pokemons - passo 03

'''
db.pokemons.distinct('types').sort()

[
  "bug",
  "dark",
  "dragon",
  "electric",
  "fairy",
  "fighting",
  "fire",
  "flying",
  "ghost",
  "grass",
  "ground",
  "ice",
  "normal",
  "poison",
  "psychic",
  "rock",
  "steel",
  "water"
]
'''

## As primeiras 3 páginas com .limit() e .skip() de pokemons (5 em 5)  - passo 04

'''
db.pokemons.find({}).limit(5).skip(5****0)

{
  "_id": ObjectId("564b1dad25337263280d047a"),
  "attack": 52,
  "created": "2013-11-03T15:05:41.271082",
  "defense": 43,
  "height": "6",
  "hp": 39,
  "name": "Charmander",
  "speed": 65,
  "types": [
    "fire"

  ]

}
{
  "_id": ObjectId("564b1dad25337263280d047c"),
  "attack": 63,
  "created": "2013-11-03T15:05:41.280718",
  "defense": 80,
  "height": "10",
  "hp": 59,
  "name": "Wartortle",
  "speed": 58,
  "types": [
    "water"

  ]

}
{
  "_id": ObjectId("564b1dad25337263280d047d"),
  "attack": 83,
  "created": "2013-11-03T15:05:41.282985",
  "defense": 100,
  "height": "16",
  "hp": 79,
  "name": "Blastoise",
  "speed": 78,
  "types": [
    "water"

  ]

}
{
  "_id": ObjectId("564b1dad25337263280d047e"),
  "attack": 30,
  "created": "2013-11-03T15:05:41.285736",
  "defense": 35,
  "height": "3",
  "hp": 45,
  "name": "Caterpie",
  "speed": 45,
  "types": [
    "bug"

  ]

}
{
  "_id": ObjectId("564b1dad25337263280d0479"),
  "attack": 56,
  "created": "2013-11-03T15:05:41.305777",
  "defense": 35,
  "height": "3",
  "hp": 30,
  "name": "Rattata",
  "speed": 72,
  "types": [
    "normal"

  ]

}
Fetched 5 record(s) in 4ms

db.pokemons.find({}).limit(5).skip(5*1)
{
  "_id": ObjectId("564b1dad25337263280d047f"),
  "attack": 20,
  "created": "2013-11-03T15:05:41.288107",
  "defense": 55,
  "height": "7",
  "hp": 50,
  "name": "Metapod",
  "speed": 30,
  "types": [
    "bug"
  
  ]

}
{
  "_id": ObjectId("564b1dad25337263280d047b"),
  "attack": 64,
  "created": "2013-11-03T15:05:41.273462",
  "defense": 58,
  "height": "11",
  "hp": 58,
  "name": "Charmeleon",
  "speed": 80,
  "types": [
    "fire"
  
  ]

}
{
  "_id": ObjectId("564b1dad25337263280d0480"),
  "attack": 45,
  "created": "2013-11-03T15:05:41.290411",
  "defense": 50,
  "height": "11",
  "hp": 60,
  "name": "Butterfree",
  "speed": 70,
  "types": [
    "flying",
    "bug"
  
  ]

}
{
  "_id": ObjectId("564b1dad25337263280d0481"),
  "attack": 60,
  "created": "2013-11-03T15:05:41.310402",
  "defense": 30,
  "height": "3",
  "hp": 40,
  "name": "Spearow",
  "speed": 70,
  "types": [
    "normal",
    "flying"
  
  ]

}
{
  "_id": ObjectId("564b1dad25337263280d0482"),
  "attack": 25,
  "created": "2013-11-03T15:05:41.294947",
  "defense": 50,
  "height": "6",
  "hp": 45,
  "name": "Kakuna",
  "speed": 35,
  "types": [
    "poison",
    "bug"
  
  ]

}
Fetched 5 record(s) in 13ms

db.pokemons.find({}).limit(5).skip(5*2)
{
  "_id": ObjectId("564b1dae25337263280d0483"),
  "attack": 65,
  "created": "2013-11-03T15:05:41.439497",
  "defense": 55,
  "height": "8",
  "hp": 52,
  "name": "Farfetchd",
  "speed": 60,
  "types": [
    "normal",
    "flying"
  
  ]

}
{
  "_id": ObjectId("564b1dae25337263280d0485"),
  "attack": 60,
  "created": "2013-11-03T15:05:41.437483",
  "defense": 95,
  "height": "10",
  "hp": 50,
  "name": "Magneton",
  "speed": 70,
  "types": [
    "steel",
    "electric"
  
  ]

}
{
  "_id": ObjectId("564b1dae25337263280d0486"),
  "attack": 85,
  "created": "2013-11-03T15:05:41.441502",
  "defense": 45,
  "height": "14",
  "hp": 35,
  "name": "Doduo",
  "speed": 75,
  "types": [
    "normal",
    "flying"
  
  ]

}
{
  "_id": ObjectId("564b1dae25337263280d0484"),
  "attack": 35,
  "created": "2013-11-03T15:05:41.435237",
  "defense": 70,
  "height": "3",
  "hp": 25,
  "name": "Magnemite",
  "speed": 45,
  "types": [
    "steel",
    "electric"
  
  ]

}
{
  "_id": ObjectId("564b1dae25337263280d0487"),
  "attack": 45,
  "created": "2013-11-03T15:05:41.445749",
  "defense": 55,
  "height": "11",
  "hp": 65,
  "name": "Seel",
  "speed": 45,
  "types": [
    "water"
  
  ]

}
Fetched 5 record(s) in 23ms
'''

## Group ou Aggregate contando a quantidade de pokemons de cada tipo - passo 05
'''
* GROUP

db.pokemons.group({
   initial: {total: 0},
   reduce: function(curr, result){ 
      curr.types.forEach(function(type){
	      if (result[type]){
		      result[type]++;
		  }else{
		      result[type] = 1;
	      }
          result.total++;
      });
    }
});

[
{
    "total": 915,
    "fire": 47,
    "water": 105,
    "bug": 61,
    "normal": 78,
    "flying": 77,
    "poison": 54,
    "steel": 37,
    "electric": 40,
    "ice": 24,
    "ghost": 34,
    "fighting": 38,
    "psychic": 62,
    "grass": 75,
    "ground": 51,
    "fairy": 28,
    "rock": 46,
    "dark": 38,
    "dragon": 20
}
]

* AGGREGATE

db.pokemons.aggregatult": [
{
      "_id": "fairy",
      "total": 28

},
{
      "_id": "psychic",
      "total": 62

},
{
      "_id": "fighting",
      "total": 38

},
{
      "_id": "dark",
      "total": 38

},
{
      "_id": "ground",
      "total": 51

},
{
      "_id": "grass",
      "total": 75
},
{
      "_id": "electric",
      "total": 40

},
{
      "_id": "steel",
      "total": 37

},
{
      "_id": "rock",
      "total": 46

},
{
      "_id": "flying",
      "total": 77

},
{
      "_id": "fire",
      "total": 47

},
{
      "_id": "ice",
      "total": 24

},
{
      "_id": "bug",
      "total": 61

},
{
      "_id": "poison",
      "total": 54

},
{
      "_id": "normal",
      "total": 78

},
{
      "_id": "ghost",
      "total": 34

},
{
      "_id": "dragon",
      "total": 20
},
{
      "_id": "water",
      "total": 105

}

],
  "ok": 1
}

'''

## Realizar 3 counts na pokemons - passo 06

'''
* Todos
db.pokemons.count();
610

* Só do tipo 'fire'
db.pokemons.count({types: 'fire'});
47

* só de quantos tem a defesa menor que 70
db.pokemons.count({defense: {$gt:70}})
250
'''

