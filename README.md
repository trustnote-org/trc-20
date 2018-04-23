### TRC-20 Token 
The TRC-20 protocol defines a common list of rules that a TrustNote based token has to implement, giving developers the ability to issue, transfer, and manage its tokens on the TrustNote network in a straightforward and easy way. A TRC-20 compatible token must adopt the UTXO account model, all its transaction records must be made public, and its total supply must be fixed.

### Method


#### Issue token
issue token，`cap` is total supply,`address` is issuer's address。

```javascript
/**
 * issue Token
 * @param {Number} cap 	   total supply
 * @param {String} address issuer's address
 * @param {} cb 		   callbacks
 */
function issueAsset(cap,address,cb)
```

#### Get balance 
Get balance of an address
```javascript
/**
 * get balance of an address
 * @param {*} assetId TokenId
 * @param {*} address address
 * @param {*} cb 	  callbacks
 */
function balanceOf(asset,address,cb)
```
#### Transfer token 

transfer token from from_address to to_address 
```javascript
/**
 * 	transfer token
 * @param {String} asset 		TokenId
 * @param {String} from_address sender's address
 * @param {String} to_address 	receiver's address
 * @param {Number} amount 		  amount 
 */
function transfer(asset,from_address,to_address,amount)
```
#### totalSupply
```javascript
/**
 *  get the total token supply
 * @param {*} TokenId   TokenId
 * @param {*} cb        callback
 */
function totalSupply(TokenId,cb)
```



#### list token
get all token id issued by this address
```javascript
/**
 * get all token id issued by this address  
 * @param {*} address issuer's address
 * @param {*} cb      callbacks
 */
function listAsset(address,cb)
```

**TRC-20 Implementation**  https://github.com/llcds/trustnote-token-en/blob/master/assetUtils.js
