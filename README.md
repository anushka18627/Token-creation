# Token-creation
#How to Create Token on Remix
// SPDX-License-Identifier: MIT
pragma solidity >=0.6.12 <0.9.0;

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

      

