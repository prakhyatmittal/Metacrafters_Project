## My metacrafter project

Tokening Solidity Smart Contract Introduction to Repository License and Version:

The SPDX-License-Identifier specifies the MIT License for this code. pragma solidity ^0.8.0; indicates compatibility with Solidity version 0.8.0 or higher. Contract Declaration:

## Token Smart Contract 

The Tokening smart contract is a versatile template designed to facilitate the creation and management of tokens on the Ethereum blockchain. Whether you're exploring token development, building a blockchain application, or simply learning Solidity, this contract provides a solid starting point.

## Code Explanations

Tokening is the name of our Solidity contract. tokenName and tokenSymbol define the name and symbol of the token, respectively. totalSupply keeps track of the total number of tokens, initialized to 0. Now, let's break down each part of the code in more detail:

### 1. Solidity Version and License
```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;
```

The SPDX-License-Identifier specifies the license for the code (MIT License in this case).
pragma solidity ^0.8.0; indicates that the contract is written in Solidity version 0.8.0 or a compatible version.
### 2. Contract Declaration

```solidity
contract MyToken {
    // Variables
    string public tokenName = "bitcoin";
    string public tokenSymbol = "BTC";
    uint256 public totalSupply = 0;
```

"Tokening" is the name of the Solidity contract.
tokenName and tokenSymbol represent the name and symbol of the token, respectively.
totalSupply stores the total number of tokens issued, initialized to 0.
### 3. Mapping

```solidity
    // Mapping
    mapping(address => uint256) public balances;
```

balances is a mapping that associates Ethereum addresses (users) with their token balances.
## Mint Function:
```solidity
    // Mint Function
    function mint(address _to, uint256 _value) external {
        totalSupply += _value;
        balances[_to] += _value;
    }
  ```
mint is an external function that allows token creation and assignment to a specified address.
It requires a valid _to address and an _value representing the number of tokens to mint.
It increases the totalSupply and adds _value tokens to the recipient's balance.

## Burn Function:
```solidity
    // Burn Function
    function burn(uint256 _value) external {
        require(balances[msg.sender] >= _value, "Sorry! You Don't Have Enough Money");
        totalSupply -= _value;
        balances[msg.sender] -= _value;
    }
```

burn is an external function enabling an address to burn (destroy) its tokens.
It requires the sender to have a sufficient balance of tokens (checked with require).
Upon burning, it reduces the totalSupply and subtracts _value from the sender's balance.

