```javascript
const SHA256 = require('crypto-js/sha256');

class Block {
    constructor(index, timestamp, data, previousHash = '') {
        // Initializing the block with an index (position in the chain), a timestamp, and the actual transaction data
        this.index = index;
        this.timestamp = timestamp;
        this.data = data;  // This is the transaction data, like sender, recipient, and amount
        this.previousHash = previousHash;  // Hash of the previous block, creating the link between blocks
        this.hash = this.calculateHash();  // Calculate the hash for this block based on its content
    }

    // Function to calculate the hash based on block's content
    calculateHash() {
        // We concatenate all block's data and hash it to get a unique block identifier
        return SHA256(this.index + this.previousHash + this.timestamp + JSON.stringify(this.data)).toString();
    }
}

class Blockchain {
    constructor() {
        // The chain is initialized with a single block: the Genesis block (first block)
        this.chain = [this.createGenesisBlock()];
    }

    // Creates the first block (Genesis Block) with default data
    createGenesisBlock() {
        // Genesis block has index 0, timestamp (current time), and some initial data
        return new Block(0, Date.now(), "Genesis Block", "0");
    }

    // Function to retrieve the last block in the chain
    getLastBlock() {
        return this.chain[this.chain.length - 1];  // Returns the last block in the blockchain
    }

    // Function to add a new block to the chain
    addBlock(newBlock) {
        // The previousHash of the new block is set to the hash of the last block
        newBlock.previousHash = this.getLastBlock().hash;

        // We now calculate the hash of the new block after setting the previous hash
        newBlock.hash = newBlock.calculateHash();

        // Add the newly created block to the chain
        this.chain.push(newBlock);
    }

    // Check the validity of the blockchain
    isChainValid() {
        // Start from the second block and iterate through the chain to verify each block
        for (let i = 1; i < this.chain.length; i++) {
            const currentBlock = this.chain[i];  // Current block being checked
            const previousBlock = this.chain[i - 1];  // Previous block to compare hashes

            // Check if the current block's hash is still valid (i.e., hasn't been tampered with)
            if (currentBlock.hash !== currentBlock.calculateHash()) {
                console.log('Current Hashes not equal');
                return false;
            }

            // Check if the current block's previous hash matches the hash of the previous block
            if (currentBlock.previousHash !== previousBlock.hash) {
                console.log('Previous Hashes not equal');
                return false;
            }
        }
        // If all checks pass, the chain is valid
        return true;
    }
}

// Test the blockchain

// Create a new blockchain instance
let BCACOIN = new Blockchain();

console.log('Mining block 1...');
// Adding the first real transaction block (block 1) with transaction data
BCACOIN.addBlock(new Block(1, Date.now(), { sender: "Akash", recipient: "Jelly", amount: 5 }));

console.log('Mining block 2...');
// Adding the second transaction block (block 2) with another transaction
BCACOIN.addBlock(new Block(2, Date.now(), { sender: "Jelly", recipient: "Akash", amount: 10 }));

// Print whether the blockchain is valid or not
console.log("Is Blockchain valid? " + BCACOIN.isChainValid());  // Should return true since we haven't tampered with the data

// Now we tamper with the data in block 1
BCACOIN.chain[1].data.amount = 15;  // Change the transaction amount in block 1
BCACOIN.chain[1].hash = BCACOIN.chain[1].calculateHash();  // Recalculate the hash after changing the data

// Check if the blockchain is still valid after tampering
console.log("Is Blockchain valid? " + BCACOIN.isChainValid());  // Should return false because the data was tampered with
```

### Comments Explanation:
1. **Block Data:**
   - Each block stores an `index`, `timestamp`, and `data` (which could be a transaction containing a sender, recipient, and amount).
   - The block's `previousHash` links it to the preceding block, ensuring the integrity of the chain.
   - The `calculateHash()` method is responsible for creating a unique hash based on the block’s content, including the data.

2. **Blockchain Data Handling:**
   - The `Blockchain` class maintains a chain of blocks. The `addBlock()` method calculates the new block's hash after including the `previousHash` from the last block, ensuring that all blocks are connected.
   - The `isChainValid()` method checks the integrity of the blockchain by recalculating each block's hash and comparing it with its stored value. If any block’s data is changed (like altering the transaction amount), the chain will be invalid.

This code and its comments provide a clear explanation of how data is handled and validated in a blockchain. Let me know if you’d like to dive deeper into any part!
