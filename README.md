### TRC-20 Token 
The TRC-20 protocol defines a common list of rules that a TrustNote based token has to implement, giving developers the ability to issue, transfer, and manage its tokens on the TrustNote network in a straightforward and easy way.

### Method


#### Define token
Define token，`definition` is asset defination,`address` is definer's address. token issuance will happen automatically while the definer transfer the asset at first time.

definition sample:
```js
var definition = {
	cap: 2000,   
	is_private: false,
	is_transferrable: true,
	auto_destroy: false,
	issued_by_definer_only: true,
	cosigned_by_definer: false,
	spender_attested: true,
  	attestors: ["ADDRESS1", "ADDRESS2"],
 	fixed_denominations: true,
  	denominations: [
        {denomination: 1, count_coins: 100},
        {denomination: 2, count_coins: 200},
        {denomination: 5, count_coins: 300}]
}
```
`cap` is the maximum amount that can be issued. 

`is_private` indicates if the asset is transferred privately or publicly.

`is_transferrable` indicates if the asset can be transferred between third parties without passing through the definer of the asset. If not transferrable, the definer must always be either the only sender or the only receiver of every transfer.

`auto_destroy` indicates if the asset is destroyed when it is sent to the definer.

`fixed_denominations` indicates if the asset can be sent in any integer amount (arbitrary amounts) or only in fixed denominations , which is the case for paper currency and coins. If true, the definition must also include the list of approved denominations.

`denominations` denominations list.

`issued_by_definer_only`	indicates	if	the	asset	can	be	issued	by	definer	only.	

`spender_attested` indicates whether the spender of the asset must be attested by one of approved attestors. If true, the definition must also include the list of approved attestor addresses.

`attestors` attestors list.

`cosigned_by_definer` indicates if every transfer must be cosigned by the definer of the asset





```javascript
/**
 * define Token
 * @param {JSON} definition 	   asset definition
 * @param {String} address         definer's address
 * @param {} cb 		   callbacks
 */
function defineAsset(definition,address,cb)
```

#### Get balance
Get balance of 
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

transfer token from from_address to to_address.
```javascript
/**
 * 	transfer token
 * @param {String} asset 		TokenId
 * @param {String} from_address sender's address
 * @param {String} to_address 	receiver's address
 * @param {Number} amount 		amount 
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

**TRC-20 Implementation**  https://github.com/trustnote/trustnote-token/blob/master/assetUtils.js
