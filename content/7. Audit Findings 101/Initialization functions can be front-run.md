
# 48 - [Initialization functions can be front-run](./Initialization%20functions%20can%20be%20front-run.md)

Initialization functions can be front-run `Hermez`, `HermezAuctionProtocol`, and `WithdrawalDelayer` have initialization functions that can be front-run, allowing an attacker to incorrectly initialize the contracts. Due to the use of the `delegatecall` proxy pattern, `Hermez`, `HermezAuctionProtocol`, and `WithdrawalDelayer` cannot be initialized with a constructor, and have initializer functions. All these functions can be front-run by an attacker, allowing them to initialize the contracts with malicious values.


1. Recommendation: Short term, either: 1) Use a factory pattern that will prevent front-running of the initialization, or 2) Ensure the deployment scripts are robust in case of a front-running attack. Carefully review the Solidity documentation, especially the Warnings section. Carefully review the pitfalls of using delegatecall proxy pattern.
2. High Risk severity finding from [ToB’s Audit of Hermez](https://github.com/trailofbits/publications/blob/master/reviews/hermez.pdf)


___
## Slide Screenshot
![048.png](../../images/7.%20Audit%20Findings%20101/048.png)
___
## Slide Text
- 
___
## References
- Youtube Reference
___
## Tags