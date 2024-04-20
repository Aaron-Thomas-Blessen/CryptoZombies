# Chapter 3: Msg.sender

Now that we have our mappings to keep track of who owns a zombie, we'll want to update the `_createZombie` method to use them.

In order to do this, we need to use something called `msg.sender`.

## msg.sender

In Solidity, there are certain global variables that are available to all functions. One of these is `msg.sender`, which refers to the address of the person (or smart contract) who called the current function.

Note: In Solidity, function execution always needs to start with an external caller. A contract will just sit on the blockchain doing nothing until someone calls one of its functions. So there will always be a `msg.sender`.

Here's an example of using `msg.sender` and updating a mapping:

```solidity
mapping (address => uint) favoriteNumber;

function setMyNumber(uint _myNumber) public {
  // Update our `favoriteNumber` mapping to store `_myNumber` under `msg.sender`
  favoriteNumber[msg.sender] = _myNumber;
  // ^ The syntax for storing data in a mapping is just like with arrays
}

function whatIsMyNumber() public view returns (uint) {
  // Retrieve the value stored in the sender's address
  // Will be `0` if the sender hasn't called `setMyNumber` yet
  return favoriteNumber[msg.sender];
}
```
## Put it to the test

Let's update our `_createZombie` method from lesson 1 to assign ownership of the zombie to whoever called the function.

1. First, after we get back the new zombie's id, let's update our `zombieToOwner` mapping to store `msg.sender` under that id.

```solidity
zombieToOwner[id] = msg.sender;
```
2. Second, let's increase `ownerZombieCount` for this `msg.sender`.

```solidity
ownerZombieCount[msg.sender]++;
```

In Solidity, you can increase a `uint` with `++`, just like in JavaScript:
```solidity
uint number = 0;
number++;
// `number` is now `1`
```
