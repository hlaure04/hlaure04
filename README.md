# ETHEREUM
Ethereum uses a computer called the Ethereum Virtual Machine (EVM), which is fundamentally a single decentralised system. 

## Description 
The contract should have public variables for coin information, a mapping of addresses to balances, a mint function that 
increases the total supply and the sender's balance, and a burn function that kills tokens. It should have conditions that 
make sure the balance of "sender" is bigger than or equal to the amount planned.

## Getting Started

### Executing Program
A web-based IDE called remix can be used to run this programme. Go to the remix site at https://remix.ethereum.org/ to get started. 
When you get to the website, click the "+" sign in the left tab to start a new file.

contract Coin {
   
// Public variables
   
    string public tokenName = "Enhypen";
    string public tokenAbbrv = "ENHY";
    uint public totalSupply = 0;

// Mapping of addresses to balances
   
    mapping(address => uint) public balances;

// Mint function
   
    function mint(address recipient, uint value) public {
        totalSupply += value;
        balances[recipient] += value;
    }

// Burn function
    
    function burn(address sender, uint value) public {
        require(balances[sender] >= value, "inadequate balance to burn.");
        totalSupply -= value;
        balances[sender] -= value;
    }
}

# Authors
Heleana V. Laure
