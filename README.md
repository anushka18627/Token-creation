# Token-creation
#How to Create Token on Remix
// SPDX-License-Identifier: MIT
pragma solidity >=0.6.12 <0.9.0;

/*
       REQUIREMENTS :
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

Introduction :
This Solidity code defines a basic ERC-20 token-like contract with functionalities for minting and burning tokens. It provides a foundational structure for creating your own custom token on the Ethereum blockchain, but additional features and security considerations are necessary for a production-ready implementation.

Description :
This code is written in Solidity language, it is the language used for developing smart contracts on blockchain. In This contract I have created 4 public variables (Token Name, Token Abbrv., Total Supply and balances)

(
  string public tokenName = "Library";
  string public tokenAbbrv = "LBR";
  uint public totalSupply = 0;)

Balances are the mapping variables of sender to keep a check on its balances. Also I have created two functions : to_mintTokens and to_burnTokens.

  function to_mintTokens(address _address,uint _value)public {
  totalSupply += _value;
  balances[_address] += _value;
 }
   function to_burnTokens(address _address,uint _value)public{
 if(_value<=balances[_address]){
 totalSupply -= _value;
 balances[_address] -=_value;
        }
       }

The to_mintTokens consists of two parameters. when we call to_mintToken function the value will be combined with the tokenSupply and balances of the sender. while in to_burnTokens it also consists of two parameters to be burnt,But there exist a conditional statement to check if the tokens to be burnt are actually available in the balances or not. if the  condition is true then the value will be deducted from both totalSupply and balances of address of the sender.


Explanation :

1. Firstly, I have created a contract named mytoken_library. The smart Contracts are basically self-executing statements or programs which are deployed in blockchain that are used to manage data. Then, I have created public variables named tokens. 
2. The token name which is the name of my token that is library (Stores the human-readable name of the token), token abbreviation that is a short form of our token name that is LBR and I have created a uint variable or an unsigned int public variable token supply initially valued as 0. this variable unsigned int public token supply is created to keep a check of number of tokens that is currently circulated or are in circulation initially the value of total supply is zero.
3. After this I have created a mapping variable here the mapping variable here is used to map the address with the unsigned int variable so that we can keep a check of balances now next we have created a mint function,function named as to_mint tokens I have passed two parameters here address and the unsigned int value or unsigned integer value
4. Next I have created the burn function that is to_burn tokens and the parameters are the same as the mint tokens that is address and the unsigned int value of address I have used this address 0x78731D3Ca6b7E34aC0F824c42a7cC18A495cabaB as an example we can use any value of address of our choice then we will deploy our code.

Execution :
1. use remix or any other platform
2. Create a new project
3. Write smart contract (the whole code)
4. Compile the contract
5. once compiled deploy the contract
6. test the working of the contract.


       contract MyToken_Library {

       // public variables here

       string public tokenName = "Library";
       string public tokenAbbrv = "LBR";
       uint public totalSupply = 0;


       // mapping variable here

       mapping(address => uint) public balances;

       // mint function

       function to_mintTokens(address _address,uint _value)public {
        totalSupply += _value;
        balances[_address] += _value;
       }
       // burn function

       function to_burnTokens(address _address,uint _value)public{
        if(_value<=balances[_address]){
            totalSupply -= _value;
            balances[_address] -=_value;
        }
       }

       }
       /*
        few addresses for testing purpose:
        0x78731D3Ca6b7E34aC0F824c42a7cC18A495cabaB
          */

      

