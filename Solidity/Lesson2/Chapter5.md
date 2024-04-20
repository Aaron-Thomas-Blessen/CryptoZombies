# Chapter 5: Inheritance

Our game code is getting quite long. Rather than making one extremely long contract, sometimes it makes sense to split your code logic across multiple contracts to organize the code.

One feature of Solidity that makes this more manageable is contract inheritance:

```solidity
contract Doge {
  function catchphrase() public returns (string memory) {
    return "So Wow CryptoDoge";
  }
}

contract BabyDoge is Doge {
  function anotherCatchphrase() public returns (string memory) {
    return "Such Moon BabyDoge";
  }
}
```
## Put it to the test

In the next chapters, we're going to be implementing the functionality for our zombies to feed and multiply. Let's put this logic into its own contract that inherits all the methods from `ZombieFactory`.

Make a contract called `ZombieFeeding` below `ZombieFactory`. This contract should inherit from our `ZombieFactory` contract.

```solidity
contract ZombieFeeding is ZombieFactory {
}
```
