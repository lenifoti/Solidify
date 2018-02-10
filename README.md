# Solidify
Framework for decentralized verification of Solidity/Ethereum/EVM Smart Contracts

This framework will allow provable verification of Smart Contracts and assignment of provable reputation to those contracts. The intent is that a Smart Contract will receive reputation when a bounty for a vulnerability cannot be claimed as well as from oracles that can prove that the contract has undergone prescribed levels of formal verification.

The framework recognises 4 participants: 
- contract-under-test is a contract that a developer wants to test and assign reputation to
- bounty-contract is a contract that offers bounties for a set of potential vulnerabilities and delivers them to successful claimants.
- claim-contract is a contract submitted by a claimant that contains code that will expose a vulnerability
- test-execution-contract is a contract that advertises bounties, accepts claims, executes the claimes and apportions rewards

