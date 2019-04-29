# Web3 Operator
> Web3 opertor is combined with web3 library for easily to interact with Ethereum

## Usage
```javascript
const Web3operator = require('web3-operator');
const web3operator = new Web3operator(web3_rpc);
```
## Functionality
* [Account_operation]('##Account_operation')
- [`createAccount(random)`]('###`createAccount(random)`')
- [`queryAccount(privateKey)`]('###`queryAccount(privateKey)`')
- [`decryptAccount(keyStoreJson, password)`]('###`decryptAccount(keyStoreJson, password)`')
- [`encryptAccount(privateKey, password)`]('###`encryptAccount(privateKey, password)`')
- [`importKey(privateKey, password)`]('###`importKey(privateKey, password)`')
* [Contract_interaction]('##Contract_interaction')
- [`compiles(contract)`]('###`compiles(contract)`')
- [`privateKeyDeploy(contract, privateKey)`]('###`privateKeyDeploy(contract, privateKey)`')
- [`accountDeploy(contract, from, password)`]('###`accountDeploy(contract, from, password)`')
- [`readContract(contract, method, parameters)`]('###`readContract(contract, method, parameters)`')
- [`accountWriteContract(from, contract, method, parameters, value, password)`]('###`accountWriteContract(from, contract, method, parameters, value, password)`')
- [`privateKeylWriteContract(contract, method, parameters, value, privateKey)`]('###`privateKeylWriteContract(contract, method, parameters, value, privateKey)`')
- [`ListeningEvent(type, host, port)`]('###`ListeningEvent(type, host, port)`')


##Account_operation

###`createAccount(random)`
    create account by random number 
###`queryAccount(privateKey)`
    query account by private key 
###`decryptAccount(keyStoreJson, password)`
    decrypt account by account keyStoreJson and account password
###`encryptAccount(privateKey, password)`
    encrypt account by account keyStoreJson and account password
###`importKey(privateKey, password)`
    import private key to node , that will convert to keyStoreJson

##Contract_interaction

###`compiles(contract)`
    compile contract from ./contract directory        
###`privateKeyDeploy(contract, privateKey)`
    use private key to deploy contract
###`accountDeploy(contract, from, password)`
    use account address and password to deploy contract
###`readContract(contract, method, parameters)`
    read indicate contract method
###`accountWriteContract(from, contract, method, parameters, value, password)`
    use account address and password to write contract
###`privateKeylWriteContract(contract, method, parameters, value, privateKey)`
    use private key to write contract
###`ListeningEvent(type, host, port)`
    listening specific event 

