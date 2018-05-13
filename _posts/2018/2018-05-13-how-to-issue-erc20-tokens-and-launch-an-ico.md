---
layout: post
title: How To Issue ERC20 Tokens And Launch An ICO
description: Explaining ERC20 token distribution, air-dropping and issuance etc while also discussing how to launch an ICO.
keywords: ico, blockchain, bitcoin, erc, ethereum, erc20, airdrop, initial coin offering, cryptocurrency
tags: [Blockchain, Cryptocurrency, Ethereum, Tutorial]
comments: true
---

Ethereum is a very powerful platform for building dApps (decentralized apps). For those that are confused about issuing tokens, they have a detailed solidity contract that can do exactly this on their webiste ([here](https://www.ethereum.org/token)). Let us walk through this sample code first.

```solidity
pragma solidity ^0.4.20;

contract MyToken {
    /* This creates an array with all balances */
    mapping (address => uint256) public balanceOf;

    /* Initializes contract with initial supply tokens to the creator of the contract */
    function MyToken(
        uint256 initialSupply
        ) public {
        balanceOf[msg.sender] = initialSupply;              // Give the creator all initial tokens
    }

    /* Send coins */
    function transfer(address _to, uint256 _value) public {
        require(balanceOf[msg.sender] >= _value);           // Check if the sender has enough
        require(balanceOf[_to] + _value >= balanceOf[_to]); // Check for overflows
        balanceOf[msg.sender] -= _value;                    // Subtract from the sender
        balanceOf[_to] += _value;                           // Add the same to the recipient
    }
}
```