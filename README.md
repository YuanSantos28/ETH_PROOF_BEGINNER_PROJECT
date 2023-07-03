# Creating a Token 
The program demonstrates the use syntaxes, mutliple data types, mapping, and the functionalities of the Solidity language. The purpose of this project is to show the basics of how Ethereum smart contracts works. 

# Description
The program is written using Remix - Ethereum IDE, which is used for smart contract development. This solidity program is a simple contract where it can store and burn tokens from 
 an address or the account holder inside the Ethereum Network.

 ## Getting Started

 ### Run the Program
to be able to use this code, you must use the Remix - Ethereum IDE website. Use this link to direct you to ther website: https://remix.ethereum.org/

Once you accessed the website, create a file and save the file as .sol. For example (Token.sol). Use this file to copy and paste the following code

```javascript

// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;
contract MyToken {

// public variables here

string public tokenName = "Yuan_Token"; 
string public tokenAbbry = "YTN";

uint public totalSupply = 0;

// mapping variable here mapping(address -> uint) public balances;
mapping  (address => uint) public balances;

// mint function
function mint (address _address, uint _value) public {
    totalSupply += _value;
    balances[_address] += _value;
}
// burn function

function burn (address _address, uint _value) public {

    if (balances[_address] >= _value) {

    totalSupply -= _value;
    balances[_address] -= _value;

    }

}

}

```
Access the "Solidity Compiler" tab in the sidebar on the left to compile the code. A compatible compiler version, such as "0.8.18," should be selected before clicking the "Compile Token.sol" button.

Using the "Deploy & Run Transactions" tab in the left sidebar, you may deploy the contract after the code has been compiled. Click the "Deploy" button after selecting the "MyToken" contract from the dropdown menu.

Once the contract was deployed, copy the account address and click on the deployed contracts. Once you click on the deployed contract, you will see mint, burn, balances, tokenAbbry, tokenName, and totalSupply. 

Clicking on tokenName will reveal the token name "Yuan_Token" and tokenAbbry will reveal the token abbreviation "YTN".

To begin transactions enter the address that you copied on mint, burn, and balances. First you must enter value in the mint function and click transact. After that check to see if the totalSupply and balances has the same amount. Let's say you entered 500 tokens from the mint, both balances and totalSupply should have " 0: uint256: 500 ".

If we are going to burn a token, enter the amount that we want to burn. Ensure that you also entered the copied address before click transact. After clicking transact you can check
the amount of tokens in your balances and totalSupply. Now let's say you burned 300 tokens,  both balances and totalSupply must have " 0: uint256: 200 ".

Now that our balance is 200, let's say you want to burn a token that is higher than your balance. 
For example you burned 250 tokens,  both balances and totalSupply will still have " 0: uint256: 200 " . 
This is because the burn function only executes if the tokens you want to burn is greater than the balance of the address

# Note
 ### * Only use one address.
 ### * You can only enter positive numbers.
 ### * The burn function only executes if the balances > the entered amount of tokens being burned.



