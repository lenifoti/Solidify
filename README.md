# Solidify
Framework for decentralized verification of Solidity/Ethereum/EVM Smart Contracts

This framework will allow provable verification of Smart Contracts and assignment of provable reputation to those contracts. The intent is that a Smart Contract will receive reputation when a bounty for a vulnerability cannot be claimed as well as from oracles that can prove that the contract has undergone prescribed levels of formal verification.

The bounty framework recognises 4 participants: 
- Contract-under-test is a contract that a developer wants to test and assign reputation to. For contracts to receive reputation in this way, they must be derived from the abstract contract "Reputable" and conform to a set of rules.
- BountyOffer contract is a contract that offers bounties for a set of potential vulnerabilities and conditions under which a reward will be released. For a contract to be able to offer a bounty, it must be derived from a 'Claimable' template and offer the bounties is a prescribed format. 
- Claim contract is a contract submitted by a bounty claimant.  This contract contains code that will expose at least one vulnerability.  The claim contract will derive from a template advertised by the offerer and contains code that should expose one or more vulnerability.
- TestExecutor contract is a contract that accepts offers and advertises them.  It then accepts claims, executes then and apportions rewards and reputation as appropriate.

# Nov 2021 update!
This project has been resurected for this hackathon.  A timeline is required to ensure that multiple claimants have an opportunity to claim. This is to remove the  a winner-takes all approach that will discourage wider partipation.  It will also payout less for simple bugs as they will be easier to spot.  There will be a premium on early submission, with a financial as well as a POAP reward for the first to claim (or the highest wager in the case that it is not claimed).
- Open: the bounty has been announced and is open for bounty submissions. To prevent copycats, the submissions are in the form of a hash (signed message of contract creation?) that is later used to match the code.
- Closed: the bounty submission phase is closed and evaluations are started. At this point the actual code can be relevealed.
- Finalisation: bounties are calculated and deliveries.
Closing and finalisation require multiple steps:
1. Upon closing, the list of submissions are checked manually (if required) and the bounty marked as payable it is obvious that they are valid. The rest are effectively left for the challenger to execute.  This must happen before Finalisation.
2. To complete each claim, the contract under test is placed in a pre-test state and the claimant's code executed to expose the vulnerability. Once this code has executed, the state is retested.  If it is not in the expected state, then the claim is marked as successful.
3. During finalisation, the successful claims are apportioned a share of the bounty according to the order in which they were submitted (first 10 with decreasing amounts)
An additional feature allows claimants to attest positively to the correctness of the contract under test.  They can do this by adding any amount to the pot. If they are successful (no-one submits a successful bounty claim, then they will share 20% of the total according to their proportion of the wagered funds.

Problems to be solved:
- The sybil problem: This needs to be solved, this reqiores proof of github or other...?
- Paying for test execution
- Scheduling the test execution - 
