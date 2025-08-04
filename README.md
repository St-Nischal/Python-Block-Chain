# Simple Blockchain in Python

This is a basic implementation of a blockchain using Python and Flask. It supports essential blockchain features such as block mining, transaction handling, and simple consensus resolution between nodes.

## Features

- Proof of Work (PoW) algorithm
- Block mining and chaining
- Transaction creation and handling
- Node registration
- Conflict resolution (Consensus algorithm)
- RESTful API using Flask

## Requirements

- Python 3.x
- Flask

You can install Flask using pip:

```bash
pip install Flask

Getting Started
1. Clone the repository

git clone https://github.com/yourusername/simple-blockchain.git
cd simple-blockchain

2. Run the server

python blockchain.py

By default, it runs on http://localhost:8000.
API Endpoints
GET /mine

Mines a new block, adds a reward transaction, and appends the block to the chain.

Response:

{
  "message": "New Block Forged",
  "index": 2,
  "transactions": [...],
  "proof": 35293,
  "previous_hash": "abc123..."
}

POST /transactions/new

Creates a new transaction and adds it to the next block.

Payload:

{
  "sender": "address_1",
  "recipient": "address_2",
  "amount": 5
}

Response:

{
  "message": "Transaction will be added to Block 2"
}

GET /chain

Returns the full blockchain and its length.

Response:

{
  "chain": [...],
  "length": 2
}

POST /node/register

Register new nodes to the network.

Payload:

{
  "nodes": ["http://localhost:8001", "http://localhost:8002"]
}

Response:

{
  "message": "New nodes have been added",
  "total_nodes": [...]
}

GET /nodes/resolve

Triggers the consensus algorithm to resolve conflicts and ensure the node has the authoritative chain.

Response:

{
  "message": "Our chain was replaced",
  "new_chain": [...]
}

or

{
  "message": "Our chain is authoritative",
  "new_chain": [...]
}

Notes

    This is a basic prototype meant for educational purposes.

    The Proof of Work algorithm used is simplistic and for demonstration only.

    There is no persistent storage (data is lost when the server restarts).
