# TodoList-Smart-Contract

## Overview

The `ToDolist` smart contract is a simple decentralized application (dApp) that allows users to create and manage a to-do list on the Ethereum blockchain. This contract provides functionalities to add new to-do items, view existing items, and toggle the completion status of items.

## Features

- Create new to-do list items
- View to-do list items by user
- View all creators and their to-do items
- Toggle the completion status of to-do items

## Contract Details

### State Variables

- **`_idUser`**: A counter to assign unique IDs to users.
- **`ownerOfContract`**: The address of the contract owner.
- **`creators`**: An array storing the addresses of users who have created to-do items.
- **`message`**: An array storing all to-do item messages.
- **`messageId`**: An array storing IDs associated with each to-do item.

### Structs

- **`ToDoListApp`**: Represents a to-do item with the following fields:
  - `account`: The address of the user.
  - `userId`: The user's unique ID.
  - `message`: The to-do item message.
  - `completed`: A boolean indicating whether the to-do item is completed.

### Events

- **`ToDoListevent`**: Emitted when a new to-do item is created, logging the user's address, ID, message, and completion status.

### Mappings

- **`toDoListApps`**: Associates an address with a `ToDoListApp` struct to store each user's to-do list data.

### Functions

- **`constructor`**: Initializes the contract, setting the deployer as the owner.
- **`inc`**: Increments the `_idUser` counter to generate unique user IDs.
- **`createList`**: Creates a new to-do list item, stores it, updates arrays, and emits an event.
- **`getCreatorData`**: Retrieves the to-do list data for a specific address.
- **`getAddress`**: Returns the array of addresses that have created to-do items.
- **`getMessage`**: Returns the array of all to-do item messages.
- **`toggle`**: Toggles the completion status of a specific user's to-do item.

## Usage

### Prerequisites

- Solidity ^0.8.0
- An Ethereum development environment (e.g., Truffle, Hardhat)

### Deployment

1. Compile the contract using your preferred Solidity compiler.
2. Deploy the contract to the Ethereum network using your preferred deployment tool (e.g., Truffle, Hardhat).

### Interacting with the Contract

#### Creating a To-Do Item

To create a new to-do item, call the `createList` function with the desired message:

```solidity
function createList(string calldata _message) external
```

#### Viewing Creator Data

To retrieve the to-do list data for a specific address, call the `getCreatorData` function with the address:

```solidity
function getCreatorData(address _address) public view returns (address, string memory, uint256, bool)
```

#### Viewing All Addresses

To get a list of all addresses that have created to-do items, call the `getAddress` function:

```solidity
function getAddress() external view returns (address[] memory)
```

#### Viewing All Messages

To get a list of all to-do item messages, call the `getMessage` function:

```solidity
function getMessage() external view returns (string[] memory)
```

#### Toggling Completion Status

To toggle the completion status of a specific user's to-do item, call the `toggle` function with the user's address:

```solidity
function toggle(address _creator) public



