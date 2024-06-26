# MyToken Solidity Contract

This Solidity program is a simple token contract that demonstrates the basic functionality of creating, minting, and burning tokens. The purpose of this contract is to provide a foundational understanding of token mechanics for those new to Solidity and blockchain development.

## Description

This contract is written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract includes:

**•** Public variables to store the token's name, abbreviation, and total supply.

**•** A mapping to track the balance of each address.

**•** A mint function to create new tokens and assign them to an address.

**•** A burn function to destroy tokens from an address, reducing the total supply.

This contract serves as an introductory example of how tokens work in the Ethereum ecosystem.


## Getting Started

### Executing program

1. To run this contract, you can go to [Remix](https://remix.ethereum.org/.), an online Solidity IDE. Follow these steps:

2. Go to the Remix website: Remix IDE.

3. Create a new file: Click on the "+" icon in the left-hand sidebar and save the file with a .sol extension (e.g., MyToken.sol).

4. Copy and paste the following code into the file:

```javascript
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;

contract MyToken {

    // Public variables to store token details
    string public name;
    string public symbol;
    uint public totalSupply;

    // Using Mapping to keep track of each address's balance
    mapping (address => uint) public balances;

    // Creating a Constructor to initialize the token details
    constructor() {
        name = "Syed";
        symbol = "Sy";
        totalSupply = 0;
    }

    // Creating a Function to mint new tokens
    function mint(address recipient, uint amount) public {
        totalSupply += amount;
        balances[recipient] += amount;
    }

    // Creating a Function to burn tokens
    function burn(address holder, uint amount) public {
        require(balances[holder] >= amount, "Insufficient balance");
        totalSupply -= amount;
        balances[holder] -= amount;
    }
}

```

5. Compile the code: Click on the "Solidity Compiler" tab in the left-hand sidebar. Ensure the "Compiler" version is set to "0.8.18" (or another compatible version), then click "Compile MyToken.sol".

6. Deploy the contract: Click on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the MyToken contract from the dropdown menu and click the "Deploy" button.

7. Interact with the contract:

**•** To mint tokens, call the mint function with the recipient's address and the amount.

**•** To burn tokens, call the burn function with the holder's address and the amount.

## Authors

Syed Raahat Gilani

[@syedraahat](https://linkedin.com/in/syedraahat)


## License

This project is licensed under the MIT License
