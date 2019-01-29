# GraphQL Basics

[The official GraphQL Documentation](https://graphql.github.io/learn/)

### Fields

GraphQL is an API query language, and a server-side runtime for executing queries by using a type system defined by the data in Keeping. 

The simplest form of a query is asking for an object from the root query, and then for one of its fields. Such a query looks like this:

### simple example
**request** 
```
{
    organisation {
        name
    }
}
```

**response**
```
{
    "data": {
        "organisation": {
            "name": "Keeping"
        }
    }
}
```

### nested example
**request**
``` 
{
    organisation {
        id,
        name,
        owner {
            id
        }
    }
}
```

**response**
```
{
    "data": {
        "organisation": {
            "id": 1,
            "name": "Keeping",
            "owner": {
                "id": 1
            }
        }
    }
}
```

The response to that query takes the same shape as the request and return exactly the data that was requested and nothing more or less. Therefore you always know what you can expect to receive in the response.

### Arguments

While the above examples are both valid queries, the Keeping API requires you to provide the id of the organisation you want to query. This is used for authorization. If you are part of the organisation that has the id you provided and you provide a valid token the request will go through. You can see an example below:

**request** 
```
{
    organisation(id: 1) {
        name
    }
}
```

**response**
```
{
    "data": {
        "organisation": {
        "name": "Keeping"
        }
    }
}
```

### Operators

Arguments will often use the string type. This is done to implement operators. The operator syntax is as follows: "value_operator". For example:

```
{
    organisation(id: 1) {
        users(id: "2_>=") {
            firstName
        }
    }
}
```

This query returns the first names of all users that have an id bigger than or equal to 2 that are a part of the organisation with the id of 1.  

## Mutations

Any query that causes data writes are explicitly sent via a mutation. For example: 

**request** 
```
mutation {
    editClientDetails(id: 9294, organisationId: 1, name: "Bob") {
        name
    }
}
```

**response**
```
{
    "data": {
        "editClientDetails": {
            "name":"Bob"
        }
    }
}
```

This mutation contains 3 arguments: 

* id - the id of the client that you want to edit the details of **(required)** 
* organisationId - the id of the organisation the client belongs to **(required)** 
* name - the information you want to edit.

This mutation returns a client object, in this case the object that is being edited. You can start querying upon this item inside the mutation as you would normally.