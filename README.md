# GrapgQl-Core

Mutation to create order

```
mutation createOrder($order: OrderInput!) {
  createOrder(order: $order) {
    id
    name
    description
    created
  }
}
```

mutation to start order
```
mutation startOrder($id:String!)
{
  startOrder(orderId:$id)
 {
  id
  status
  name
 }
}
```
query to getorder

```
query getOrder {
  
  orders{
    id
    name
    description
    customer
    {
      id
      name
    }
    created
  }
}

```
variables
```
{
   "order":{
        "name": "test order2",
        "description": "Another order2",
        "created": "01-01-2018",
        "customerId": 1
  },
   "id": "b32493c7-3202-4375-852b-f468630ee5bd"
}
```
subscription1
```
subscription{
  orderEvent(statuses:[CREATED])
    {
      orderId
      name
      status
    }
}
```
subscription2
```

subscription{
  orderEvent(statuses:[PROCESSING])
    {
      orderId
      name
      status
    }
}
```
