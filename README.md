# 491 Blockchain Implementaiton 
Repostiory based off the hackernoon python implentation of a blockchain.


## Prerequisites
1. Python v. 3.6+ 
2. Curl 
3. Docker 


## Create a new node/Initalze the network 

 1. Python blockchain.py 
 2. Python blockchain.py -p
 3. Python blockchain.py --port (default is 5000)

## Mine a block
```
 curl http://localhost:5000/mine
```
## Send a transaction 
```
 curl -X POST -H "Content-Type: application/json" -d '{
 "sender": "A adresss",
 "recipient": "someone-other-address",
 "amount": 5
 }' "http://localhost:5000/transactions/new"
```

## Put a node into the trusted network 
The blockchain by default creates two sepearte chains when a new port is created.
Use This command to connect two nodes to the same blockchain. 

```
  curl -X POST -H "Content-Type: application/json" -d '{"nodes": ["http://localhost:5000","http://localhost:5001"]
  }' "http://localhost:5000/nodes/register"
  ```

## Resolve conflicts with the length of a chain between nodes
```
 curl http://localhost:5000/nodes/resolve
```

