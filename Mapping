// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract MyToken {
    string public name; // Token Name
    string public symbol; // Token Abbrv.
    uint256 public totalSupply; // Total Supply

    mapping(address => uint256) public balances; // Mapping of addresses to balances

    constructor(string memory _name, string memory _symbol, uint256 _totalSupply) {
        name = _name;
        symbol = _symbol;
        totalSupply = _totalSupply;
        balances[msg.sender] = _totalSupply; // Assign total supply to contract creator
    }

    // Mint function
    function mint(address account, uint256 value) public {
        totalSupply += value; // Increase total supply
        balances[account] += value; // Increase balance of the recipient
    }

    // Burn function
    function burn(address account, uint256 value) public {
        require(balances[account] >= value, "Insufficient balance");
        totalSupply -= value; // Decrease total supply
        balances[account] -= value; // Decrease balance of the sender
    }
}
