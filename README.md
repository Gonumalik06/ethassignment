MyToken Smart Contract

Overview
MyToken is a simple ERC-20-like smart contract implemented in Solidity. This contract allows the creation, minting, and burning of a token named "META" with the abbreviation "MTA". It includes basic functionalities for managing token balances, including minting new tokens and burning existing ones.
Features
Public Variables:
tokenName: The name of the token ("META").
tokenAbbrv: The abbreviation of the token ("MTA").
totalSupply: The total supply of the token, initially set to 0.

Balances Mapping:

A mapping from addresses to their respective balances. This tracks the number of tokens held by each address.
Mint Function:

The mint function allows for the creation of new tokens. It takes two parameters: an address and a value. The total supply of tokens is increased by the specified value, and the balance of the specified address is increased by the same amount.

Burn Function:
The burn function allows for the destruction of tokens. It takes two parameters: an address and a value. The total supply of tokens is decreased by the specified value, and the balance of the specified address is decreased by the same amount. This function includes a check to ensure that the address has a sufficient balance to burn the specified amount of tokens.

Usage
Deploying the Contract
To deploy the MyToken contract, you need a Solidity development environment such as Remix, Truffle, or Hardhat. Deploy the contract using your preferred method, and the initial state will have a total supply of 0 tokens.

Minting Tokens
To mint new tokens, call the mint function with the desired address and the amount of tokens to mint. This will increase both the total supply of tokens and the balance of the specified address
.mint(address _address, uint _value).
_address: The address to which the minted tokens will be assigned.
_value: The amount of tokens to mint.

Burning Tokens
To burn existing tokens, call the burn function with the desired address and the amount of tokens to burn. This will decrease both the total supply of tokens and the balance of the specified address, provided the address has a sufficient balance.

solidity
burn(address _address, uint _value)
_address: The address from which the tokens will be burned.
_value: The amount of tokens to burn.

Example
Here's an example of how to use the mint and burn functions:
solidity
// Mint 100 tokens to address 0x123...
myToken.mint(0x123..., 100);

// Burn 50 tokens from address 0x123...
myToken.burn(0x123..., 50);

License
This project is licensed under the MIT License. See the LICENSE file for details.

Conclusion
MyToken provides a straightforward implementation of a token contract with basic minting and burning functionality. This can serve as a foundation for more complex token contracts and decentralized applications.

source code with the readme file .

// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
*/

contract MyToken {

    // public variables here
    string public tokenName = "META";
    string public tokenAbbrv = "MTA";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
   function mint  (address _address, uint _value) public {
    totalSupply += _value; // corrected here from _values to _value
    balances[_address] += _value; // corrected here from _values to _value
    }

    // burn function
   function burn (address _address, uint _value) public {
    if (balances[_address] >= _value) {
    totalSupply -= _value; // corrected here from _values to _value
    balances[_address] -= _value; // corrected here from _values to _value
}
        }
}








