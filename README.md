# Description

The ErrorHandling contract demonstrates how to use require, revert, and assert statements in Solidity for error handling.

### Executing Program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

pragma solidity ^0.5.0;

contract ErrorHandling {
    function checkRequire(uint value) public pure {
        require(value <= 5, "Value is greater than 5");
    }

    function checkRevert(uint value) public pure {
        if (value > 1) {
            if (value > 2) {
                if (value > 10) {
                    revert("Value is greater than 10");
                }
            }
        }
    }

    uint public storedNumber = 100;

    function verifyAssert() public view {
        assert(storedNumber == 100);
    }
}

# Author
MetaCrafter Gian

# License
This project is licensed under the MIT License - see the LICENSE.md file for details
