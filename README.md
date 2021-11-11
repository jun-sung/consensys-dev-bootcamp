# Consensys Blockchain Developer Bootcamp 2020

Below are the projects and dapps I completed as part of the 2020 cohort.


## [Coding my own Blockchain from Scratch in Python3 - blockchain.py](https://github.com/jun-sung/consensys-dev-bootcamp/blob/main/blockchain.py)

- Implemented a simple Proof-of-Work algorithm similar to HashCash
- Deployec Python Flask to communicate with blockchain through http requests
- Deployed Postman to interact with blockchain (create new transaction, mine new block, return full blockchain)
- Implemented consensus algorithm by checking chains in other nodes and finding the longest valid chain


## [Generating Ethereum Accounts in Javascript](https://github.com/jun-sung/consensys-dev-bootcamp/tree/main/ethereum-address-generator-js)

- Learning public key cryptography and digital signatures
- Generate a private key, derive public keys from the private key and verify associated accounts

## [Using Geth (Go-Ethereum)](https://github.com/jun-sung/consensys-dev-bootcamp/tree/main/geth-poa-tutorial-master)

- Geth (Go-Ethereum) is a command line interface for running a full Ethereum node implemented in Go
- Geth is used to mine real Ether, transfer funds between addresses, create contracts and send transactions, and explore block history
- Learned my way around the geth javascript console ($ geth console)
- Created private blockchain with proof of work consensus mechanism (test-private-blockchain)

    #### [genesis.json](https://github.com/jun-sung/consensys-dev-bootcamp/blob/main/genesis.json)
    - `config`: defines settings for private blockchain
    - `chainId`: identifies blockchain
    - `alloc`: allows creation of addresses and fills account with ether upon initialization of blockchain - left empty in order to fill accounts by mining ether
    - `difficulty`: indicates how difficult to discover valid hash of block - defines mining target - calculated according to previous block difficulty and timestamp - difficulty indicates how many average calculations miner will have to complete to find block - value fluctuates to maintain target block generation time
    - `extraData`: optional 32 byte value to add information
    - `gasLimit`: sets chain-wide limit of gas expenditure per block
    - `parentHash`: keccak256 hash of parent block's header
    - `timestamp`: output of Unix time() function at block's creation (in calculating difficulty) allows verification of order of blocks in the chain
    - Created new account
    - Mined private chain
    - Sent transaction
    - Verified balance

- Created private blockchain with proof of authority consensus mechanism (geth-poa)
    - Implemented native geth proof-of-authority protocol clique
    - Configured clique via puppeth for creating custom genesis blocks
    - Used bootnode to act as a router/hub where all nodes pass information and receive information from this node
    - Launched node1 with genesis block (node1 is a mining node)
    - Launched node2 and node3 to interact with blockchain
    - Sent transactions from nodes to each other

---

## Writing Smart Contracts

### [Proof of Existence (proof-of-existence)](https://github.com/jun-sung/consensys-dev-bootcamp/tree/main/proof-of-existence)

- Implemented `ganache-cli` for development blockchain
- Hands-on practice using Truffle's `create`, `migrate`, `console`
- Created three versions: one proof, array of proofs, mapping of proofs
- Deployed to Rinkeby testnet via Infura

### [Multi-Signature Wallet (MultiSignatureWallet.sol)](https://github.com/jun-sung/consensys-dev-bootcamp/tree/main/multisig-wallet-exercise)

- Multisignature wallet: an account requiring some m-of-n quorum of approved private keys to approve a transaction before executing
- Learned how to handle complex interactions between multiple users on one contract
- Learned to avoid loops and implement voting
- Audited for attacks on smart contracts
- Learned best practices for implementing `modifiers`, `events`/`emit`, `index` keywords
- Hands-on practice using Truffle's `develop` to interact with contract

### [Exercise: SimpleBank](https://github.com/jun-sung/consensys-dev-bootcamp/tree/main/simple-bank-exercise-jun-sung)

- Setup banking functions with `getBalance`, `enroll`, `deposit`, `withdraw`
- Implemented through `mapping`, `event` references

### [Exercise: SupplyChain](https://github.com/jun-sung/consensys-dev-bootcamp/tree/main/supply-chain-exercise-jun-sung)

- Imitated standard supplychain functions with `ForSale`, `Sold`, `Shipped`, `Received`
- Implemented through `mapping`, `struct`, `enum`, `event`, `modifier`
