// SPDX-License-Identifier: MIT
pragma solidity 0.8.0;
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
