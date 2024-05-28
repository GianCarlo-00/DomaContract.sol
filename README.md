# Description

 This contract demonstrates how to use require, revert, and assert statements in Solidity for Example Item and Prices.

### Executing Program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

pragma solidity ^0.8.0;

contract PriceHandler {
    mapping(string => uint256) public prices;

    event PriceSet(string itemName, uint256 price);

    function setPrice(string memory _itemName, uint256 _price) external {
        require(_price > 0, "Price must be greater than zero");

        assert(_price <= 10000 ether); 

        if (bytes(_itemName).length == 0) {
            revert("Item name must not be empty");
        }

        prices[_itemName] = _price;
        emit PriceSet(_itemName, _price);
    }

    function getPrice(string memory _itemName) external view returns (uint256) {
        return prices[_itemName];
    }
}


# Author
MetaCrafter Gian

# License
This project is licensed under the MIT License - see the LICENSE.md file for details.
