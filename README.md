# Create a Token

This solidity program is a simple program that demonstrates how a token is minted and burned using Solidity language. 

## Description

This solidity program is a simple program that demonstrates how a token is minted and burned. The mint function adds value to the token based on the inputted amount. Meanwhile, the burn function decreases the value of the token. Also, the burn function has a condition that the balance must be greater than or equal to the value to be burned.  

## Getting Started

### Executing program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the following code into the file:

```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

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
    //Token Name, Token Abbrv., Total Supply
    string public TokenName = "Doge";  
    string public TokenAbbrv = "Dog"; 
    uint public TotalSupply = 0; 
    

    // mapping variable here
    mapping (address => uint) public balances;

    // mint function
   function mint (address _add, uint _val) public {
      TotalSupply = TotalSupply + _val; 
      balances[_add] = balances[_add] + _val; 
   }

    // burn function
   function burn (address _add, uint _val) public {
      while (balances[_add] >= _val){
      TotalSupply = TotalSupply - _val; 
      balances[_add] = balances[_add] - _val;

      break; 
      }
   }
}
```
To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.4" (or another compatible version), and then click on the "Compile solidity_assessment.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the "Deploy" button was clicked and successful, the "Deployed Contracts" must have a drop-down button option to expand the functions contained in the code. The "burn" and "mint" function contains a drop-down button to simplify inputting the address and the value to be inserted to the token. 



## Authors

Paul Adrian T. Gernale
FEU Tech


## License

This project is licensed under the MIT License. 
