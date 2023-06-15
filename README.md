# Contracts_Assesment
This Solidity program is a simple "contract" program that demonstrates the basic syntax and functionality of the Solidity programming language. 
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

## Getting Started
### Executing program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension 

```javascript
pragma solidity ^0.8.4;

contract MyToken {

    // public variables here
         string public TokenName="CLIFF";
         string public tokenAbbrv="CF";
         uint public totalSupply=0;

```
৹ This is declarations of public variables.



```javascript
 // mapping variable here
        mapping (address=>uint) public balances;
       
```
৹ This maps the adreess with the value.
ie, we give address and the respective value mapped with the address is returned.

```javascript
 // mint function
        function mint(address _address, uint _value) public {
            totalSupply+=_value;
            balances[_address]+=_value;
        }
```
৹ The Mint Function is used for minting or adding the values to totalsupply and balances array.


```javascript
  // burn function
         function burn(address _address, uint _value) public {
             if(balances[_address]>=_value){
            totalSupply-=_value;
            balances[_address]-=_value;
             }
        }
```
৹ This Burn Function is used to remove the values from the total supply and a conditional statement is used that is if the tokens value entered is more than available burn function will not execute.

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.4" (or another compatible version), and then click on the "Compile token.sol" button.
Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "HelloWorld" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the created functions.
