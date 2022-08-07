MongoDB Commands
=======

## Create
- inserOne
- insertMany
## Update
- updateOne
- updateMany
- replaceOne
## Read
- find
- findOne
## Delete
- deleteOne
- deleteMany

## Run in CLI
###
```yml
mongo
```
```yml
show dbs
```
```yml
use <dbname>
```
```yml
show collections
```
```yml
db.<collectionName>.findOne()
```
```yml
db.<collectionName>.find()
```
```yml
db.<collectionName>.find().pretty()
```
```yml
db.<collectionName>.count()
```
```yml

db.movies.find({name:"Titanic"})
```
```yml
db.movies.find({rating:{$gte:4}})
```
```yml
db.movies.insertOne({
})
```
```yml

db.movies.insertOne([
    {},{},{}
])
```
```yml

db.movie.updateOne({name:"Titanic"},{$set:{"rating":5}})
```
```yml
### Add new column or filed in all documents
db.movie.updateMany({},{$set:{"country":"India"}})
```
```yml

## Remove a field in all documents
db.movie.updateMany({name:"Titanic"},{$unset:{"rating":""}})
```
```yml

## Rename a field in all documents
db.movie.updateMany({},{$rename:{"rating":"rating_customer"}})
```
```yml

## Replace document
## Remove a field in all documents
db.movie.update({name:"Titanic"},{name:"Titanic_New",rating:3.5})
```
```yml

db.movie.delete({name:"Titanic"})
```
```yml
db.movie.deleteMany({year:2001})
```
```yml
## Delete entire data in collection
db.movie.deleteMany({})
```
```yml
db.movie.drop()
```
```yml
db.dropDatabase()
```
```yml

db.movie.find({},{name:1,year:1,_id:0})
```
```yml

## Regex
db.movie.find({description:{$regex:/idiot/}})
```
```yml

db.movie.find({"actors.name":"Leo"})
```
```yml

## Add document in array
db.movie.updateMany({name:"Titanic"},{$push:{"actors":{name:"Remo",age:45}}})
```
```yml
## Remove document in array
db.movie.updateMany({name:"Titanic"},{$pull:{"actors":{name:"Remo"}}})
```
```yml

db.move.find({genre:["drama","romance"]})
```
```yml

