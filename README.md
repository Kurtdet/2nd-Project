MyToken

Description

This Solidity contract, MyToken, is a simple implementation of an ERC-like token that allows for the minting and burning of tokens. The contract includes essential functionalities such as managing the token name, abbreviation, total supply, and user balances. This project serves as an introductory example for those looking to understand the basics of token creation and management on the Ethereum blockchain.

Getting Started

Executing the Program

To run this contract, you can use Remix, an online Solidity IDE. Follow the steps below to get started:

Go to the Remix website at https://remix.ethereum.org/.

Create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., MyToken.sol).

Copy and paste the following code into the file:

solidity
Copy code

// SPDX-License-Identifier: MIT

pragma solidity 0.8.18;

contract MyToken {

    string public tokenName = "META";
    string public tokenAbbrv = "MTA";
    uint public totalSupply = 0;
    
    mapping(address => uint) public balances;
    
    function mint (address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }
    
    function burn (address _address, uint _value) public {
        require(balances[_address] >= _value, "Insufficient balance to burn.");
        totalSupply -= _value;
        balances[_address] -= _value;
    }
}

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile MyToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button.

After deploying the contract, you can interact with it by using the mint and burn functions. You can specify the address and value for minting and burning tokens.
