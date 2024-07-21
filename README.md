Error Handling Explained
Error handling in Solidity is crucial for writing robust smart contracts. The contract demonstrates three primary methods for handling errors:

require: This statement is used to enforce conditions that must be met for the function to proceed. If the condition is not met, the transaction is reverted, and an optional error message is returned. It is typically used for input validation and access control.

Example: Ensuring only the owner can update the data.
```
require(msg.sender == owner, "Only the owner can update the data");
```
revert: This statement is used to conditionally revert the transaction based on some logic. It is often used inside if statements for more complex condition checks. revert also provides an optional error message.

Example: Preventing unauthorized users from performing an action.
```
if (msg.sender != owner) {
    revert("You are not authorized to perform this action");
}
```
assert: This statement is used to check for conditions that should never occur. It is primarily used for internal error checking and invariants. If the condition fails, the transaction is reverted, and all gas is consumed.

Example: Ensuring a new value is within a specific range.
```
assert(newValue < upperLimit);
```
Deployment and Usage
Deploy the contract using Remix, Hardhat, or any other Ethereum development framework.
Interact with the contract using the deployed instance:
Call updateData to update the data variable (only callable by the owner).
Call restrictedAction to perform a restricted action (only callable by the owner).
Call alwaysTrueInvariant to update the data variable within a specified range.
