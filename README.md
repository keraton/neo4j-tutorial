# Neo4J Cypher Tutorial

## Cypher principles

* Cypher match pattern of Nodes and Relationship in the graph, to extract information or modify data the data.
* Cypher has concept of identifier which denote named, bound elements and parameters.
* Cypher can create, update, and removes nodes, relationships, labels and properties.
* Cypher manage indexes and constraints.

## Cypher indentifier

In order to work with cypher language, we need to use the identifier.

```
MATCH (n:Person)
Where n.name = 'Jack'
RETURN *

```

In this example _n_ is used as a identifier.
It is similar to SQL identifier.

```
Select *
From Person n
Where n.name = 'Jack'
```

## Create Node

To create a Node, use the keyword Create.

```
CREATE (n{name: 'Jack'} )
``` 

We can also create a Node with a Label.
Label can be used as a tag, or even a type of a node.

```
CREATE (n:Person {name: 'Jack'})
```

## Match a node

We use MATCH keywords to find a node.

```
MATCH (n:Person)
 WHERE n.name = 'Jack'
 RETURN *
```

## Create a relation

In order to create a relation, we need at least two nodes.
First create another node.

```
CREATE (w:Movie {name: 'Star Wars'})
```

Now create a relation where Jack like Star Wars.

```
MATCH (n:Person) WHERE n.name = 'Jack'
MATCH (m:Movie) WHERE m.name = 'Star Wars'
CREATE (n) -[:LIKES] -> (m)
```

We can also add some properties to the relationship.
Create a new node.

```
CREATE (w:Movie {name: 'Star Trek'})
WITH w
MATCH (n:Person) WHERE n.name = 'Jack
CREATE (n) -[:HATE {since : '1969'}] -> (m)
```

The Keyword WITH is needed between CREATE and MATCH to specify explicitly the identifier.

## Match a relation

Find all the moves that related to a person

```
MATCH (n:Person{name :'Jack'}) --> (m:Movies)
RETURN m
```

Find all the movies that a person like/hate

```
MATCH (n:Person{name :'Jack'}) -[:LIKE]-> (m:Movies)
RETURN m
```

## Your turn

Build a catalogue of Movie and Person.

Anna like Taxi
John like Kungfu
Anna Hate Kungfu
Anna like Star Wars
Jack like Kungfu

Find all person that like Kungfu.

## Lets work with real movies

type
```
:play movie-graph
```

See what we can do.






