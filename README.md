# How-to-use-my-smart-contract-on-Redbelly
How to use a smart contract I created on Redbelly Devent

# AnitaOgbogu Token

The AnitaOgbogu token (ANTZ) is an ERC20 token on the Ethereum blockchain that can be transferred between addresses.

## Contract details 

Name: Anita Ogbogu

Symbol: ANTZ

Decimals: 18

Total Supply: 100000000000

## Function

The main functions available in the contract are:

### transfer

Transfers an amount of tokens from the sender to a recipient address.

``` bash
function transfer(address recipient, uint256 amount) public
```

### Parameters

recipient - The address to receive the token transfer

amount - The amount of tokens to transfer

### Requirements

The sender must have a token balance greater than or equal to the transfer amount

### Returns

(No return, it executes the transfer)

### Example

``` bash
AnitaOgbogu.transfer(0x1234567890123456789012345678901234567890, 1000) // Transfers 1000 ANTZ to recipient address
```

This transfers 1000 ANTZ tokens from the sender's address to the provided recipient address. The sender must have a balance of at least 1000 tokens for this to succeed.

### Accessing Balance

To read the ANTZ token balance of an address, use the balances mapping like:

``` bash
uint256 balance = AnitaOgbogu.balances(address);
```

Replace address with the wallet address you want to check.

### Deploying the Contract

#### To deploy this contract on a network like Ethereum mainnet:

Compile the contract using solc

Get ABI and bytecode

In web3 provider (ethers.js, web3.js etc), use ABI & bytecode to deploy

##### Example:

``` bash 
const abi = [ABI here];
const bytecode = 'Bytecode here'...

const AnitaOgbogu = new web3.eth.Contract(abi);

AnitaOgbogu.deploy({
  data: bytecode 
}).send({
  from: myWalletAddress 
}).on('receipt', (receipt) => { 
  // Success!
});
```

This will deploy the contract to the network and create the ANTZ token that can then be transferred using the transfer function.

Let me know if you have any other questions!
