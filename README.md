# Web3 Operator
> Web3 opertor is combined with web3 library for easily to interact with Ethereum

- [Web3 Operator](#web3-operator)
  - [Usage](#usage)
  - [Account_operation](#accountoperation)
    - [`createAccount(random)`](#createaccountrandom)
    - [`queryAccount(privateKey)`](#queryaccountprivatekey)
    - [`decryptAccount(keyStoreJson, password)`](#decryptaccountkeystorejson-password)
    - [`encryptAccount(privateKey, password)`](#encryptaccountprivatekey-password)
    - [`importKey(privateKey, password)`](#importkeyprivatekey-password)
  - [Contract_interaction](#contractinteraction)
    - [`compiles(contract)`](#compilescontract)
    - [`privateKeyDeploy(contract, privateKey)`](#privatekeydeploycontract-privatekey)
    - [`accountDeploy(contract, from, password)`](#accountdeploycontract-from-password)
    - [`readContract(contract, method, parameters)`](#readcontractcontract-method-parameters)
    - [`accountWriteContract(from, contract, method, parameters, value, password)`](#accountwritecontractfrom-contract-method-parameters-value-password)
    - [`privateKeylWriteContract(contract, method, parameters, value, privateKey)`](#privatekeylwritecontractcontract-method-parameters-value-privatekey)
    - [`accountToLoopWriteContract(from, contract, method, parameters, value, password, loopTime, endTime)`](#accounttoloopwritecontractfrom-contract-method-parameters-value-password-looptime-endtime)
    - [`privateKeyToLoopWriteContract(contract, method, parameters, value, privateKey, loopTime, endTime)`](#privatekeytoloopwritecontractcontract-method-parameters-value-privatekey-looptime-endtime)
    - [`ListeningEvent(type, host, port)`](#listeningeventtype-host-port)

## Usage
```javascript
const Web3operator = require('web3-operator');
const web3operator = new Web3operator(web3_rpc);
```

## Account_operation
### `createAccount(random)`
create account by random number 
* `random` - `String`: random string 
```javascript
web3operator.createAccount(random)
// > return account detail
```

### `queryAccount(privateKey)`
query account by private key 
* `privateKey` - `String`: private key
```javascript
web3Operator.queryAccount(privateKey)
// >  return account detail
```
### `decryptAccount(keyStoreJson, password)`
decrypt account by account keyStoreJson and account password
* `keyStoreJson` - `Object` if your account created in local node, it should store in ./node/keyStore
* `password` - `String`: sender account password
```javascript
web3Operator.decryptAccount(keyStoreJson, password)
// >  return account detail (include private key)
```

### `encryptAccount(privateKey, password)`
encrypt account by account keyStoreJson and account password
* `privateKey` - `String`: private key
* `password` - `String`: sender account password
```javascript
web3Operator.encryptAccount(privateKey, password)
// >  return keyStoreJson
```

### `importKey(privateKey, password)`
import private key to node , that will convert to keyStoreJson
* `privateKey` - `String`: private key
* `password` - `String`: sender account password
```javascript
web3Operator.importKey(privateKey, password)
// >  
```

## Contract_interaction

### `compiles(contract)`
compile contract from ./contract directory        
* `contract` - `String`: contract name
```javascript
web3Operator.compiles(contract)
// >  return contract compiled and the compiled data in ./contract_detail directory
```

### `privateKeyDeploy(contract, privateKey)`
use private key to deploy contract
* `contract` - `String`: contract name
* `privateKey` - `String`: private key
```javascript
web3Operator.privateKeyDeploy(contract, privateKey)
// >  return transaction receipt , recommand to find contractAddress attribute for contract iteraction 
```

### `accountDeploy(contract, from, password)`
use account address and password to deploy contract
* `contract` - `String`: contract name
* `from` - `Address`: sender account address
* `password` - `String`: sender account password
  
```javascript
web3Operator.accountDeploy(contract, from, password)
// >  return transaction receipt , recommand to find contractAddress attribute for contract iteraction 
```

### `readContract(contract, method, parameters)`
read indicate contract method
* `contract` - `String`: contract name
* `method` - `String`: contract function name
* `parameters` - `Array`: contract function parameters 

```javascript
web3Operator.readContract(contract, method, parameters)
// >  return contract data
```

### `accountWriteContract(from, contract, method, parameters, value, password)`
use account address and password to write contract
* `from` - `Address`: sender account address, mean 
* `contract` - `String`: contract name
* `method` - `String`: contract function name
* `parameters` - `Array`: contract function parameters 
* `value` - `Number`: ether value
* `password` - `String`: sender account password
  
```javascript
web3Operator.accountWriteContract(from, contract, method, parameters, value, password)
// >  return transaction receipt
```

### `privateKeylWriteContract(contract, method, parameters, value, privateKey)`
use private key to write contract
* `contract` - `String`: contract name
* `method` - `String`: contract function name
* `parameters` - `Array`: contract function parameters 
* `value` - `Number`: ether value
* `privateKey` - `String`: private key

```javascript
web3Operator.privateKeylWriteContract(contract, method, parameters, value, privateKey)
// >  return transaction receipt
```

### `accountToLoopWriteContract(from, contract, method, parameters, value, password, loopTime, endTime)`
use private key to write contract for loop before  endTime, after respond the amount of confirmed transaction

* `from` - `Address`: sender account address, mean 
* `contract` - `String`: contract name
* `method` - `String`: contract function name
* `parameters` - `Array`: contract function parameters 
* `value` - `Number`: ether value
* `password` - `String`: sender account password
* `loopTime` - `Number`: send transaction in loop 
* `endTime` - `Number`: the time for finish loop send transaction process 
  
```javascript
web3Operator.accountToLoopWriteContract(from, contract, method, parameters, value, password, loopTime, endTime)
// >  return num of contract transaction verified in endTime : 
```

### `privateKeyToLoopWriteContract(contract, method, parameters, value, privateKey, loopTime, endTime)`
use private key to write contract for loop before  endTime, after respond the amount of confirmed transaction

* `contract` - `String`: contract name
* `method` - `String`: contract function name
* `parameters` - `Array`: contract function parameters 
* `value` - `Number`: ether value
* `privateKey` - `String`: private key
* `loopTime` - `Number`: send transaction in loop
* `endTime` - `Number`: the time for finish loop send transaction process 
  
```javascript
web3Operator.privateKeyToLoopWriteContract(contract, method, parameters, value, privateKey, loopTime, endTime)
// >  return num of contract transaction verified in endTime : 
```

### `ListeningEvent(type, host, port)`
listening specific event 
* `type` - `String` can be `logs`、`pendingTransactions`、`syncing`
* `host` - `String` websocket host
* `port` - `String` websocket port

```javascript
web3Operator.ListeningEvent(type, host, port)
// >  listening 
```

