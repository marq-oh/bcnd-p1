# Project: Create Your Own Private Blockchain

## Background
See [Original Instructions]

## Project Definition
This is the first project in my BlockChain Developer course and is a requirement for completion. The intent of the project is to demonstrate learnings in creating a basic Private BlockChain using NodeJs. 

## Wallet
1. The [Electrum Wallet] was used during development and testing. Please visit the Electrum website for instructions on how to set up
2. When creating an Electrum Wallet, please select 'Legacy' as this is what is supported by a library (bitcoinjs-message) that is used in the code. i.e. Wallet address should start with 1. (e.g. 1J4NExPjTf2ZXNaMjk3fTAjYVr2PDq48UQ)
3. To sign a message, go to  Tools > Sign/Verify Message

## Endpoints

### GET '/block/0'
- Fetches genesis block
- Returns: (example)

```
{
    "hash": "f1f0731a1b23c9c742360395442732e1b0c3e7522c1be41efe3853e0b6f27ea8",
    "height": 0,
    "body": "7b2264617461223a2247656e6573697320426c6f636b227d",
    "time": "1587855155",
    "previousBlockHash": null
}
```

### POST '/requestValidation'

- To request for ownership

```
{
	"address":"19yQz2gtojeb9n2nkhxhu8AD6b265eVkZZ"
}
```

- Returns: (example)

```
"19yQz2gtojeb9n2nkhxhu8AD6b265eVkZZ:1587855868:starRegistry"
```

### POST '/requestValidation'

- To submit star

```
{
	"address":"1J4NExPjTf2ZXNaMjk3fTAjYVr2PDq48UQ",
	"signature":"INfgH85vKnZ6g7FxI6/K6T7FQ9Vii9pvA2o+hbzC5sBJNKzIRkXi/ekQ8BStnV07BZSaNjqefvUeqlLYB8GK49Q=",
	"message":"1J4NExPjTf2ZXNaMjk3fTAjYVr2PDq48UQ:1587855261:starRegistry",
     "star": {
         "dec": "5° 0' 8.0",
         "ra": "5h 0m 8.0s",
         "story": "Testing the other story444444"
     }
}
```

- Returns: (example)

```
{
    "hash": "2da1fb54aec2cca04dbecb22c86eb3a4866a2c53fedf753f6afd7778043da8d2",
    "height": 1,
    "body": "7b226f776e6572223a22314a344e4578506a5466325a584e614d6a6b336654416a5956723250447134385551222c2273746172223a7b22646563223a2235c2b020302720382e30222c227261223a22356820306d20382e3073222c2273746f7279223a2254657374696e6720746865206f746865722073746f7279343434343434227d7d",
    "time": "1587856715",
    "previousBlockHash": "8efcd38a8c0e0aaf86e72877a034defcea878fd70f4845ac20b6c47cdedb9e65"
}
```

### GET '/blocks/[address]'
- Fetches blocks for specified address
- Returns: (example)

```
[
    {
        "owner": "1J4NExPjTf2ZXNaMjk3fTAjYVr2PDq48UQ",
        "star": {
            "dec": "5Â° 0' 8.0",
            "ra": "5h 0m 8.0s",
            "story": "Testing the other story 3"
        }
    },
    {
        "owner": "1J4NExPjTf2ZXNaMjk3fTAjYVr2PDq48UQ",
        "star": {
            "dec": "5Â° 0' 8.0",
            "ra": "5h 0m 8.0s",
            "story": "Testing the other story 4"
        }
    }
]
```

## Author

Marco SJ
