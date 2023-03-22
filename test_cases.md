# NFT Delegation Smart Contract
## Sample Test Cases

[How and where to run the test cases?](#setupEnvrionment)\
[Register a delegation address on The Memes by 6529 collection.](#registerDelegationAddressCollection)\
[Register a delegation address using a wallet with subdelegation rights](#)\
[Check consolidation between two addresses](#)\
[Retrieve delegation address](#)\
[Retrieve delegators](#)\
[How does it work for project developers?](#)

<div id='setupEnvironment'/>

## Setup workscape:

The easiest way to run the sample test cases is via remix.org.

1. Navigate to remix.org
2. Under File Explorer click the Create New file icon
3. Name the file testCases.sol
4. Navigate to the src folder on the [nftdelegation repository](https://github.com/6529-Collections/nftdelegation/blob/main/src/DelegationManagement.sol)
5. Copy the source code and paste it on the newly created testCases.sol
6. Under Solidity compiler click Compile testCases.sol
7. Navigate to the Deploy & run transactions tab
8. Make sure that the Envrionment is set to Remix VM (Merge) and the Contract is set to delegationManagementContract
9. Click Deploy and then Force Send

If you followed the steps correctly you will be able to view all setter and getter functions of the smart contract.\

You are always welcome to run the smart contract code and conduct the tests using other tools.

<div id='registerDelegationAddressCollection'/>

## Register a delegation address on The Memes by 6529 collection.

Description: In this group of test cases a wallet calls the registerDelegationAddress(...) function to register or not a delegation address. Please make sure that the wallet address 0x5B38Da6a701c568545dCfcB03FcB875f56beddC4 is selected as an Account on remix and that you will use as a delegation Address an address that also exists on the Account dropdown box.\

### Test Case ID: 1

Test Case Objective: Register a delegation address on 0x33FD426905F149f8376e227d0C9D3340AaD17aF1 (The Memes by 6529 collection address) for all use cases (1-15).\
\
Prerequisite:
1. Usecase number exists 
2. Delegation Address is not locked
<!-- end of the list -->

Input Data:\
\
_collectionAddress = 0x33FD426905F149f8376e227d0C9D3340AaD17aF1\
_delegationAddress = 0xdD870fA1b7C4700F2BD7f44238821C26f7392148\
_expiryDate = 1682080764 (21/04/2023)\
_useCase = 1\
_allTokens = true\
_tokenid = 0\
\
Expected Output: The delegation will be registered.\
\
Actual Output: The delegation was registered.\
\
Status: Pass

### Test Case ID: 2

Test Case Objective: Register a delegation address on 0x33FD426905F149f8376e227d0C9D3340AaD17aF1 (The Memes by 6529 collection address) just for the airdrop use case and just for The Memes token #1.\
\
Prerequisite:
1. Use case number exists
2. Delegation Address is not locked
<!-- end of the list -->

Input Data:\
\
_collectionAddress = 0x33FD426905F149f8376e227d0C9D3340AaD17aF1\
_delegationAddress = 0xdD870fA1b7C4700F2BD7f44238821C26f7392148\
_expiryDate = 1682080764 (21/04/2023)\
_useCase = 3\
_allTokens = false\
_tokenid = 1\
\
Expected Output: The delegation will be registered.\
\
Actual Output: The delegation was registered.\
\
Status: Pass


### Test Case ID: 3

Test Case Objective: Register a delegation address on 0x33FD426905F149f8376e227d0C9D3340AaD17aF1 (The Memes by 6529 collection address) with use case number 50.\
\
Prerequisite:
1. Delegation Address is not locked
<!-- end of the list -->

Input Data:\
\
_collectionAddress = 0x33FD426905F149f8376e227d0C9D3340AaD17aF1\
_delegationAddress = 0xdD870fA1b7C4700F2BD7f44238821C26f7392148\
_expiryDate = 1682080764 (21/04/2023)\
_useCase = 50\
_allTokens = true\
_tokenid = 0\
\
Expected Output: The delegation will not be registered as the execution of the transaction will fail.\
\
Actual Output: The delegation was not registered.\
\
Status: Pass



    
