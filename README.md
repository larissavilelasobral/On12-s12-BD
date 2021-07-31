<h1 align="center">
    <br>
    <p align="center">Semana 12 - Introdução ao Banco de Dados<p>
</h1>

## Para Casa

![exercise](https://media1.popsugar-assets.com/files/thumbor/XGbRY5FyWX99jE-AVcO0vx7A008/fit-in/1024x1024/filters:format_auto-!!-:strip_icc-!!-/2017/04/26/922/n/1922283/a08d3bf8b558b4c9_giphy_4_/i/When-Your-BFF-Tells-You-First-Name-Guy-She-Going-Date-You-Spring-CIA-Mode.gif)

Você deve criar um banco de dados novo (database) e uma coleção com um nome pertinente, de acordo com os dados e tema que você escolher. Os seguintes comandos devem ser feitos e entregues:

* Inserção de documentos
* Atualização de documentos
* Exclusão de documentos
* Consulta com projeção
* Consulta utilizando combinação entre os seletores
* Consulta paginada e ordenada (utilizar *skip*, *limit* e *sort*)

```
    "Agent": {
	"name": " ",
        "nationality": " ",
	"Role": " "
    },
    "others": { 
	"Skills": [],
        "Biography": ""
    }
```
_________________
_Atualizar documento: 
ˋˋˋ
db.getCollection('Agents').update(
    // query 
    {
        "Agent.name" : "Sage"
    },
    {
    // update 
        $set: { "Agent.Role" : "Sentinel"
        }
    },
    
    // options 
    {
        "multi" : true,  // update only one document 
         // insert a new document, if no existing document match the query 
    }
);
ˋˋˋ

_Exclusão de documentos_:
ˋˋˋ
db.getCollection('Agents').remove({ 'Agent.Role' : 'DUELIST' });
ˋˋˋ

_Consulta com projeção_

````
db.getCollection('Agents').find({'others.Skills' : {$elemMatch:{'others.Skills': [0]}}})

````
não funciona

_Consulta utilizando combinação entre seletores_
```
db.Agents.find({'Agent.name':{$ne:'brimstone'}})

```

_Consulta Paginada e ordenada(skip, limit e sort)_

````
db.Agents.find().skip(1).limit(2)
```
