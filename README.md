Flashcard System Smart Contract

This Solidity smart contract, FlashcardSystem, provides a decentralized platform for creating and managing flashcards on the Ethereum blockchain. Users can create flashcards with questions and answers, and retrieve their content by ID.

Features

1. Create a Flashcard

Function: createFlashcard(string calldata question, string calldata answer)

Description:

Allows users to create a flashcard with a question and an answer.

Each flashcard is assigned a unique ID.

Emits a FlashcardCreated event upon successful creation.

Requirements:

question and answer cannot be empty strings.

2. View a Flashcard

Function: viewFlashcard(uint256 flashcardId)

Description:

Retrieves the details of a flashcard by its unique ID.

Returns the question, answer, and the timestamp of creation.

Requirements:

The flashcard must exist; otherwise, an error is thrown.

Contract Components

1. Struct: Flashcard

Represents a flashcard with the following fields:

question: The text of the question.

answer: The text of the answer.

timestamp: The creation timestamp of the flashcard.

2. State Variables

mapping(uint256 => Flashcard) public flashcards;

Stores flashcards by their unique ID.

uint256 public flashcardIdCounter;

Tracks the total number of flashcards created and ensures unique IDs.

3. Events

event FlashcardCreated(uint256 indexed flashcardId, string question, string answer);

Logs the creation of a flashcard.

Deployment

Use a Solidity-compatible environment such as Remix, Hardhat, or Truffle.

Ensure the Solidity compiler version is ^0.8.0.

Deploy the contract to your desired Ethereum network.

Usage

Creating a Flashcard

Call the createFlashcard function with the desired question and answer. Example:

createFlashcard("What is Solidity?", "A programming language for Ethereum smart contracts.");

Viewing a Flashcard

Retrieve a flashcard's details using its unique ID. Example:

(string memory question, string memory answer, uint256 timestamp) = viewFlashcard(1);

Error Handling

Question cannot be empty: Triggered if the question is an empty string.

Answer cannot be empty: Triggered if the answer is an empty string.

Flashcard not found: Triggered if no flashcard exists for the provided ID.

License

This project is licensed under the MIT License.
