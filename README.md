# Solidify
Framework for decentralized verification of Solidity/Ethereum/EVM Smart Contracts

This framework will allow provable verification of Smart Contracts and assignment of provable reputation to those contracts. The intent is that a Smart Contract will receive reputation when a bounty for a vulnerability cannot be claimed as well as from oracles that can prove that the contract has undergone prescribed levels of formal verification.

The bounty framework recognises 4 participants: 
- Contract-under-test is a contract that a developer wants to test and assign reputation to. For contracts to receive reputation in this way, they must be derived from the abstract contract "Reputable" and conform to a set of rules.
- BountyOffer contract is a contract that offers bounties for a set of potential vulnerabilities and conditions under which a reward will be released. For a contract to be able to offer a bounty, it must be derived from a 'Claimable' template and offer the bounties is a prescribed format. 
- Claim contract is a contract submitted by a bounty claimant.  This contract contains code that will expose at least one vulnerability.  The claim contract will derive from a template advertised by the offerer and contains code that should expose one or more vulnerability.
- TestExecutor contract is a contract that accepts offers and advertises them.  It then accepts claims, executes then and apportions rewards and reputation as appropriate.


