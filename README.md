## MY TOKEN.SOL
This is a basic Solidity smart contract for a token called "MyToken". 

## DESCIRPTION
The code is a Solidity smart contract for a basic token called "MyToken". It also has two public variables for the token name and abbreviation, and a total supply variable. It also has a mapping variable called "balances" which maps addresses to their token balances.
This contract has two functions called "mint" and "burn". The "mint" function  adds the given value to the balance of the specified address. The "burn" function  reduces the balance of the specified address by the given value, but only if the address has sufficient balance.

## GETTING STARTED
We have to use remixIDE to compile and run and deploy the program.

## EXECUTING THE PROGRAM
* CREATE A NEW FOLDER NAMED MYTOKEN.SOL
* WRITE THE CONTRACT IN SOLIDITY 
* IF THE REMIX IS ON AUTO COMPILE AND RUN,THE WRITTEN CODE WILL BE COMPILED AND RUN AUTOMATICALLY BUT IF IT IS NOT ON AUTO COMPILE THEN WE HAVE TO MANUALLY COMPILE AND   RUN THE CODE BY SELECTING THE OPTION AS COMPILE AND RUN IN THE LEFT MENU
* AFTER COMPILING WE DEPLOY THE CONTRACT THEN WE GET THE ACCOUNT ADDRESS WHICH WE USE IN FURTHER STEPS
* THEN IF THE CODE IS DEPLOYED SUCCESSFULLY WE CAN CHECK THE TOKEN NAME AND TOKEN ABBREVIATION.
* BY CLICKING ON TOKENABBVR WE CAN CHECK THE TOKEN ABBREVIATION AND SIMILARLY WE CAN CHECK TOKEN SUPPLY AND TOKeN NAME TOOO.
* INITIALLY WE WILL HAVE 0 BALANCE IN OUR ACCOUNT 
* FOR MINTING WE CLICK ON MINt BUTTON THEN WE PASTE THE ACCOUNT ADDRESS (WE HAVE PROVIDED AFTER DEPLOYING THE CONTRACT) THEN WE PUT VALUE OF HOW MUCH TOKEN WE HAVE TO     MINT SUPPOSE LETS TAKE 200 TOKENS THEN CLICK TRANSACT.(TOKENS WILL BE TRANSACTED IN THE ACCOUNT)
* TO CHECK THR BALANCE CLICK ON  BALANCES THEN PASTE ACCOUNT ADDRESS THEN CLICK ON CALL WE WILL GET THE ACCOUNT BALANCE
* THEN TO BURN SOME TOKENS WE WILL CLICK ON BURN AND THEN PASTE ACCOUNT ADDRESS THEN SET THE VALUE TO 70 (70 TOKENS WILL BE BURNT FROM OUR ACCOUNT)
* TO CHECK BALANCE AGAIN PRESS ON CALL WE WILL GET THE LATEST BALANCE. 200-70=130 (130 WILL BE THE LATEST BALANCE).
* THIS IS ALL FOR THE CONTRACT.


## CONTRACT 

// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;


contract MyToken {

    // public variables here
   string public tokenName ="MRUNAL";
   string public tokenAbbvr= "MRU";
   uint public totalSupply=0;
    // mapping variable here
   mapping(address=> uint) public balances;
    // mint function

   function mint (address _address, uint _value) public {
    totalSupply +=_value;
    balances[_address] += _value;
   }
    // burn function
   function burn (address _address,uint _value) public {
       if(balances[_address]>=_value)
       {
         totalSupply -=_value;
         balances[_address] -= _value;
       }
    
   }
}
