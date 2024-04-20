# Chapter 6: Import

Whoa! You'll notice we just cleaned up the code to the right, and you now have tabs at the top of your editor. Go ahead, click between the tabs to try it out.

Our code was getting pretty long, so we split it up into multiple files to make it more manageable. This is normally how you will handle long codebases in your Solidity projects.

When you have multiple files and you want to import one file into another, Solidity uses the `import` keyword:

```solidity
import "./someothercontract.sol";

contract newContract is SomeOtherContract {

}
```
## Put it to the test

Now that we've set up a multi-file structure, we need to use `import` to read the contents of the other file:

Import `zombiefactory.sol` into our new file, `zombiefeeding.sol`.

```solidity
import "./zombiefactory.sol";
```
