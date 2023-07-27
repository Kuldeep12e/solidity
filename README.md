
# Token Creation in Solidity

This project contains a smart contract written in Solidity that implements a basic coin contract with minting and burning functionality. The contract allows the creation and destruction of tokens while keeping track of token balances for each address.


## Contract details
The contract includes the following public variables:

1. tokenName: A string representing the name of the token.
2. tokenAbbrv: A string representing the abbreviated name of the token.
3. totalSupply: An unsigned integer representing the total supply of tokens in circulation.
## Mapping of Addresses to Balances
The contract uses a mapping to keep track of the token balances for each address. The mapping is defined as follows:

mapping(address => uint) balances;
## Mint Function
The mint function increases the total supply of tokens and the balance of a specific address. It takes two parameters:
 the address and the amount or the value.
## Burn Function
The burn function reduces the total supply of tokens and deducts tokens from a specific address. It takes two parameters:
the address
and the value

The burn function includes conditionals to ensure that the balance of the address is greater than or equal to the amount to be burned. If the balance is insufficient, the function will not proceed with the burning process and will throw an exception.
## Executing Program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the following code into the file:
## code

// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;



contract MyToken {

    // public variables here
	string public tokenName = "META";
	string public tokenAbbry = "MTA";
	uint public  totalSupply = 0;

    // mapping variable here
    mapping(address => uint)public balances;
    // mint function
	function mint(address _address , uint _value)public{
		totalSupply += _value;
		balances[_address] += _value; 
	}
    // burn function
	function burn(address _address , uint _value)public{
		if(balances[_address] >= _value){
			totalSupply -= _value;
			balances[_address] -= _value; 
		}
		
	}


}
    
## Usage
To deploy and interact with the contract, you will need an Ethereum development environment (such as Remix or Truffle) or a wallet that supports smart contract interactions. Once deployed, you can call the mint and burn functions with appropriate parameters to create or destroy tokens.

Note: Make sure to review and test the contract thoroughly before deploying it on the mainnet or any production environment. Additionally, ensure proper access controls and security mechanisms are implemented to protect against potential vulnerabilities.
## Disclaimer
This code is provided as-is with no warranties or guarantees. The authors are not responsible for any potential issues or losses that may arise from the use of this code. Use it at your own risk.
## Author
Kuldeep Yadav