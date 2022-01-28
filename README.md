# Fita Cart

## Description
This is an implementation of fita cart in Go (Golang) projects.

### How To Run This Project
> Make Sure you have run the database/20220121081800_cart.sql in your mysql


Since the project already use Go Module, I recommend to put the source code in any folder but GOPATH.

#### Run the Testing

```bash
$ make test
```

#### Run the Applications
Here is the steps to run it with `docker-compose`

```bash
#move to directory
$ cd workspace

# Clone into YOUR $GOPATH/src
$ git clone https://github.com/williamchand/fita-cart.git

#move to project
$ cd fita-cart

# Build the docker image first
$ make docker

# Run the application
$ make run

# check if the containers are running
$ docker ps

# Execute the call
$ curl localhost:9090/fita-cart

# Stop
$ make stop

## Query add cart
```
mutation AddCart($sku: String, $quantity: Int) {
  AddCart(sku: $sku, quantity: $quantity) {
    id
    items_id
    quantity
  }
}

```
### Query variables
```
{
  "quantity": 1,
  "sku": "120P90"
}
```
## Query order items at cart
```
mutation ConfirmOrder($placeholder: String) {
  ConfirmOrder(placeholder: $placeholder) {
    id
    total_price
  }
}
```

### Query variables
```
{
  "placeholder": ""
}
```
