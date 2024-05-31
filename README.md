SimpleToken Smart Contract
Overview
The SimpleToken smart contract is a basic implementation of a token management system on the Ethereum blockchain. It allows the contract owner to mint new tokens and users to transfer tokens and check their balances.
Features
* Minting Tokens: The contract owner can mint new tokens to any address.
* Transferring Tokens: Users can transfer tokens to other addresses.
* Checking Balances: Anyone can check the token balance of any address.
Contract Details
State Variables
* mapping(address => uint256) private balances: A mapping that stores the token balance for each address.
* address public owner: The address of the contract owner, set at the time of contract deployment.
Events
* event Mint(address indexed to, uint256 amount): Emitted when new tokens are minted.
* event Transfer(address indexed from, address indexed to, uint256 amount): Emitted when tokens are transferred between addresses.
Modifiers
* modifier onlyOwner(): Restricts access to certain functions to only the contract owner. If the caller is not the owner, the function call will be reverted with an error message.
Constructor
* constructor(): Sets the contract deployer as the owner.
Functions
mint
solidity

function mint(address to, uint256 amount) public onlyOwner

function mint(address to, uint256 amount) public onlyOwner
* Description: Mints new tokens to a specified address.
* Parameters:
    * to: The address to receive the newly minted tokens.
    * amount: The amount of tokens to mint.
* Requirements:
    * Only the contract owner can call this function.
    * The to address cannot be the zero address.
* Events: Emits a Mint event upon successful minting.
transfer
solidity

function transfer(address to, uint256 amount) public

function transfer(address to, uint256 amount) public
* Description: Transfers tokens from the caller's address to another address.
* Parameters:
    * to: The address to receive the tokens.
    * amount: The amount of tokens to transfer.
* Requirements:
    * The to address cannot be the zero address.
    * The caller must have a sufficient balance to transfer the specified amount.
* Events: Emits a Transfer event upon successful transfer.
balanceOf
solidity

function balanceOf(address account) public view returns (uint256)

function balanceOf(address account) public view returns (uint256)
* Description: Returns the token balance of a specified address.
* Parameters:
    * account: The address to query the balance of.
* Returns: The token balance of the specified address.
Usage
1. Deploying the Contract:
    * Deploy the SimpleToken contract on the Ethereum network.
    * The deployer will be set as the contract owner.
2. Minting Tokens:
    * The owner can call the mint function to create new tokens and assign them to a specified address.
3. Transferring Tokens:
    * Users can call the transfer function to send tokens from their address to another address.
4. Checking Balances:
    * Anyone can call the balanceOf function to check the token balance of any address.
License
This project is licensed under the MIT License. See the LICENSE file for details.
