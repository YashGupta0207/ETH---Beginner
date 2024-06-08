# Token

Solidity is a high-level programming language specifically designed for implementing smart contracts on the Ethereum blockchain. It was created to enable the writing of decentralized applications (dApps) that run on the Ethereum Virtual Machine (EVM).

## Description

This contract defines a simple token with the name and abbreviation. It includes basic minting and burning functionality:

1- Minting: Increases the total supply and the balance of a specified address.

2- Burning: Decreases the total supply and the balance of a specified address, provided the address has enough tokens.

The contract stores the token name, abbreviation, and total supply, maps addresses to their token balances, and includes functions to mint and burn tokens.
## Getting Started

### Executing program

To run this program, use Remix, an online Solidity IDE. Visit the Remix website at Remix IDE, create a new file by clicking the "Crete File" icon in the left-hand sidebar, and save it with a '.sol' extension (e.g., Token.sol). Copy and paste the provided code into the file, which includes functions to mint and burn tokens.
```
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
    uint public total_supply = 0;
    string public t_name = "FERNO";
    string public t_abbr = "FRN";

    // mapping variable here
    mapping(address => uint) public balance;

    // mint function
    function mint(address _add, uint _val) public { 
    total_supply +=_val;
    balance[_add] += _val;
    }
    // burn function
    function burn(address _add, uint _val) public {
        if(balance[_add]>=_val){
        total_supply -=_val;
        balance[_add] -=_val;
        }
    }
}

```
To compile the code, navigate to the "Solidity Compiler" tab on the left sidebar in Remix. Ensure the "Compiler" version is set to 0.8.18 or another compatible version, then click "Compile MyToken.sol."
After successful compilation, proceed to deploy the contract by going to the "Deploy & Run Transactions" tab on the left sidebar. Choose the "MyToken" contract from the dropdown menu and press the "Deploy" button.

With the contract deployed, you can interact with it by using the provided functions. To mint new tokens, select the mint function, input the recipient's address and the amount of tokens to mint, and click "transact." To burn tokens, select the burn function, input the address and the quantity of tokens to burn, then click "transact."

These steps will allow you to test and manage your token contract using Remix.

## Authors
YASH GUPTA
@YASHGUPTA

## License

This project is licensed under the MIT LICENSE - see the LICENSE.md file for details
