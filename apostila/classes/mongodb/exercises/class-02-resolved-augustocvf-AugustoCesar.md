# MongoDB - Aula 02 - Exerc�cio
autor: Augusto Cesar Vieira Forment�o

## 1. Crie uma database chamada be-mean-pokemons;

  > use be-mean-pokemons
  switched to db be-mean-pokemons

## 2. Liste quais databases voc� possui nesse servidor;

  > show dbs
  be-mean            0.078GB
  be-mean-aula2      0.078GB
  be-mean-instagram  0.078GB
  local              0.078GB

## 3. Liste quais cole��es voc� possui nessa database;

  > show collections
  >

## 4. Insira pelo menos 5 pokemons A SUA ESCOLHA utilizando o mesmo padr�o de campos utilizado: name, description, attack, defense e height;

var pokemons = {name:"Blastoise",description:"Tartaruga azul turbinada com canh�es de �gua",type:"�gua",attack:200,defense:100,height:0.4}
db.pokemons.insert(pokemons)
var pokemons = {name:"Charizard",description:"Evolu��o do Charmaleon",type:"fogo",attack:500,defense:900,height:0.9}
db.pokemons.insert(pokemons)
var pokemons = {name:"Onix",description:"Este Pok�mon tem um �m� em seu c�rebro que serve como uma b�ssola interna",type:"pedra",attack:400,defense:800,height:1.9}
db.pokemons.insert(pokemons)
var pokemons = {name:"Kakuna",description:"forma evolu�da de Weedle",type:"Inseto",attack:100,defense:300,height:0.5}
db.pokemons.insert(pokemons)
var pokemons = {name:"Beedrill",description:" � a forma final de Weedle. Pode Mega Evoluir com a pedra Beedrilite.",type:"Inseto",attack:500,defense:500,height:0.7}
db.pokemons.insert(pokemons)
var pokemons = {name:"Butterfree",description:"Duas antenas e grandes olhos vermelhos.Suas asas possuem um p� que cai continuamente enquanto ele voa",type:"Inseto",attack:100,defense:100,height:0.7}
db.pokemons.insert(pokemons)


## 5. Liste os pokemons existentes na sua cole��o;

> db.pokemons.find()
{ "_id" : ObjectId("56440deac4cc9e7d0f84aae4"), "name" : "Blastoise", "description" : "Tartaruga azul turbinada com canh
�es de �gua", "type" : "�gua", "attack" : 200, "defense" : 100, "height" : 0.4 }
{ "_id" : ObjectId("56440e25c4cc9e7d0f84aae5"), "name" : "Charizard", "description" : "Evolu��o do Charmaleon", "type" :
 "fogo", "attack" : 500, "defense" : 900, "height" : 0.9 }
{ "_id" : ObjectId("56440e33c4cc9e7d0f84aae6"), "name" : "Onix", "description" : "Este Pok�mon tem um �m� em seu c�rebro
 que serve como uma b�ssola interna", "type" : "pedra", "attack" : 400, "defense" : 800, "height" : 1.9 }
{ "_id" : ObjectId("56440e4bc4cc9e7d0f84aae7"), "name" : "Kakuna", "description" : "forma evolu�da de Weedle", "type" :
"Inseto", "attack" : 100, "defense" : 300, "height" : 0.5 }
{ "_id" : ObjectId("56440e58c4cc9e7d0f84aae8"), "name" : "Beedrill", "description" : " � a forma final de Weedle. Pode M
ega Evoluir com a pedra Beedrilite.", "type" : "Inseto", "attack" : 500, "defense" : 500, "height" : 0.7 }
{ "_id" : ObjectId("56440e69c4cc9e7d0f84aae9"), "name" : "Butterfree", "description" : "Duas antenas e grandes olhos ver
melhos.Suas asas possuem um p� que cai continuamente enquanto ele voa", "type" : "Inseto", "attack" : 100, "defense" : 1
00, "height" : 0.7 }



## 6. Busque o pokemons a sua escolha, pelo nome, e armazene-o em uma vari�vel chamada `poke`;

> var query = {name: 'Blastoise'}
> var poke = db.pokemons.findOne(query)
> poke
{
        "_id" : ObjectId("56440deac4cc9e7d0f84aae4"),
        "name" : "Blastoise",
        "description" : "Tartaruga azul turbinada com canh�es de �gua",
        "type" : "�gua",
        "attack" : 200,
        "defense" : 100,
        "height" : 0.4
}
>


## 7. Modifique sua `description` e salv�-o

> poke.description
Tartaruga azul turbinada com canh�es de �gua
> poke.description = 'Eles podem disparar balas de �gua com precis�o suficiente para atacar latas vazias de uma dist�nci
a de mais de 160 p�s'
Eles podem disparar balas de �gua com precis�o suficiente para atacar latas vazias de uma dist�ncia de mais de 160 p�s
> poke
{
        "_id" : ObjectId("56440deac4cc9e7d0f84aae4"),
        "name" : "Blastoise",
        "description" : "Eles podem disparar balas de �gua com precis�o suficiente para atacar latas vazias de uma dist�
ncia de mais de 160 p�s",
        "type" : "�gua",
        "attack" : 200,
        "defense" : 100,
        "height" : 0.4
}
> db.pokemons.save(poke)
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })
> db.pokemons.find(query)
{ "_id" : ObjectId("56440deac4cc9e7d0f84aae4"), "name" : "Blastoise", "description" : "Eles podem disparar balas de �gua
 com precis�o suficiente para atacar latas vazias de uma dist�ncia de mais de 160 p�s", "type" : "�gua", "attack" : 200,
 "defense" : 100, "height" : 0.4 }

