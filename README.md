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








