## $Lookup

- The $lookup is typically used when you have a collection that contains a field with a reference to another collection. By using $lookup, you can retrieve the referenced documents and merge them with the original document in a single query.

The $lookup takes several arguments, including the name of the collection to join, the local field that contains the reference, the foreign field that is being referenced, and the name of the new field that will hold the joined documents.


```
db.orders.aggregate([
  {
    $lookup: {
      from: "products",
      localField: "productId",
      foreignField: "_id",
      as: "product"
    }
  }
])


```
