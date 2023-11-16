MyToken Solidity Contract
This Solidity contract, named MyToken, introduces a simple implementation of a token with basic functionalities such as minting and burning. It adheres to the specified requirements outlined below.

Requirements
Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply).
Your contract will have a mapping of addresses to balances (address => uint).
You will have a mint function that takes two parameters: an address and a value. The function then increases the total supply by that number and increases the balance of the “sender” address by that amount.
Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. It will take an address and value just like the mint functions. It will then deduct the value from the total supply and from the balance of the “sender”.
Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal to the amount that is supposed to be burned.
Contract Details
Token Name: meta
Token Abbreviation: mta
Total Supply: 0
Public Variables
solidity
Copy code
string public tokenName = "meta";
string public tokenAbbrev = "mta";
uint public totalSupply = 0;
Mapping Variable
solidity
Copy code
mapping(address => uint) public balance;
Mint Function
solidity
Copy code
function mint(address _address, uint _value) public {
    totalSupply += _value;
    balance[_address] += _value;
}
The mint function increases the total supply by the specified value and increases the balance of the specified address by that amount.

Burn Function
solidity
Copy code
function burn(address _address, uint _value) public {
    require(balance[_address] >= _value, "Insufficient balance");
    totalSupply -= _value;
    balance[_address] -= _value;
}
The burn function destroys tokens by deducting the specified value from the total supply and the balance of the specified address. It includes a conditional check to ensure that the balance of the "sender" is greater than or equal to the amount that is supposed to be burned.
