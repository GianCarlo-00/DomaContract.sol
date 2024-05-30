# Description

This contract demonstrates how to use require, revert, and assert statements in Solidity.

### Executing Program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

pragma solidity ^0.8.0;

contract EmailContract {
    mapping(address => string) public userEmails; 

    event EmailAdded(address indexed account, string email);
    event EmailUpdated(address indexed account, string newEmail);

    function addEmail(string memory email) public {
        assert(bytes(email).length > 0);
        userEmails[msg.sender] = email; 
        emit EmailAdded(msg.sender, email);
    }

    function updateEmail(string memory newEmail) public {
        assert(bytes(newEmail).length > 0);
        userEmails[msg.sender] = newEmail; 
        emit EmailUpdated(msg.sender, newEmail);
    }

    function removeEmail() public {
        require(bytes(userEmails[msg.sender]).length > 0, "No email address to remove");
         
         if(bytes(userEmails[msg.sender]).length == 0) {
        revert("No email address to remove");
        }
        delete userEmails[msg.sender];
    }
}



# Author
MetaCrafter Gian

# License
This project is licensed under the MIT License - see the LICENSE.md file for details.
