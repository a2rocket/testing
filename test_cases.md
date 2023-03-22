# NFT Delegation Smart Contract
## Sample Test Cases

[How and where to run the test cases?](#setupEnvironment)\
[Register a delegation address on The Memes by 6529 collection.](#registerDelegationAddressCollection)\
[Revoke a delegation address on The Memes by 6529 collection.](#revokeDelegationAddress)\
[Update a delegation address on The Memes by 6529 collection.](#updateDelegationAddress)\
[Register a delegation address using a wallet with subdelegation rights](#registerDelegationAddressUsingSubDelegation)\
[Revoke a delegation address using a wallet with subdelegation rights](#revokeDelegationAddressUsingSubdelegation)\
[Check consolidation between two addresses - pending](#)\
[Retrieve delegation address - pending](#)\
[Retrieve delegators - pending](#)\
[How does it work for project developers? - pending](#)

<div id='setupEnvironment'/>

## Setup workscape:

The simpliest cinfiguration to run the sample test cases is via remix.org.

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

### Description: In this group of test cases a wallet calls the registerDelegationAddress(...) function to register a delegation address. Please make sure that the  address 0x5B38Da6a701c568545dCfcB03FcB875f56beddC4 is selected as an Account on remix and that you will use as a delegation Address an address that also exists on the Account dropdown box.

### Test Case ID: 1

***Test Case Objective:*** \
\
Register a delegation address on 0x33FD426905F149f8376e227d0C9D3340AaD17aF1 (The Memes by 6529 collection address) for all use cases (1-15).\
\
***Prerequisite:***
1. Usecase number exists 
2. Delegation Address is not locked
<!-- end of the list -->

***Input Data:***\
\
_collectionAddress = 0x33FD426905F149f8376e227d0C9D3340AaD17aF1\
_delegationAddress = 0xdD870fA1b7C4700F2BD7f44238821C26f7392148\
_expiryDate = 1682080764 (21/04/2023)\
_useCase = 1\
_allTokens = true\
_tokenid = 0

***Post-execution:***\
\
Call the retrieveDelegationAddresses(...) function with inputdata _delegatorAddress = 0x5B38Da6a701c568545dCfcB03FcB875f56beddC4, _collectionAddress = 0x33FD426905F149f8376e227d0C9D3340AaD17aF1, _useCase = 1 and the function will return the delegation address 0xdD870fA1b7C4700F2BD7f44238821C26f7392148.

Function | Use-Case  | Expected Output | Actual Output | Status
------------- | ------------- | ------------- | ------------- | -------------
registerDelegationAddress(...) | 1 | The delegation will be registered. | The delegation was registered. | Pass


### Test Case ID: 2

***Test Case Objective:*** \
\
Register a delegation address on 0x33FD426905F149f8376e227d0C9D3340AaD17aF1 (The Memes by 6529 collection address) for the airdrop use case (#3) only and just for The Memes token #1.\
\
***Prerequisite:***
1. Use case number exists
2. Delegation Address is not locked
<!-- end of the list -->

***Input Data:***\
\
_collectionAddress = 0x33FD426905F149f8376e227d0C9D3340AaD17aF1\
_delegationAddress = 0xdD870fA1b7C4700F2BD7f44238821C26f7392148\
_expiryDate = 1682080764 (21/04/2023)\
_useCase = 3\
_allTokens = false\
_tokenid = 1

***Post-execution:***\
\
Call the retrieveDelegationAddresses(...) function with inputdata _delegatorAddress = 0x5B38Da6a701c568545dCfcB03FcB875f56beddC4, _collectionAddress = 0x33FD426905F149f8376e227d0C9D3340AaD17aF1, _useCase = 3 and the function will return the delegation address 0xdD870fA1b7C4700F2BD7f44238821C26f7392148.

Function | Use-Case  | Expected Output | Actual Output | Status
------------- | ------------- | ------------- | ------------- | -------------
registerDelegationAddress(...) | 3 | The delegation will be registered. | The delegation was registered. | Pass

### Test Case ID: 3

Test Case Objective: Register a delegation address on 0x33FD426905F149f8376e227d0C9D3340AaD17aF1 (The Memes by 6529 collection address) for use case number 50.\
\
***Prerequisite:***
1. Delegation Address is not locked
<!-- end of the list -->

***Input Data:***\
\
_collectionAddress = 0x33FD426905F149f8376e227d0C9D3340AaD17aF1\
_delegationAddress = 0xdD870fA1b7C4700F2BD7f44238821C26f7392148\
_expiryDate = 1682080764 (21/04/2023)\
_useCase = 50\
_allTokens = true\
_tokenid = 0

***Post-execution:***\
\
Call the retrieveDelegationAddresses(...) function with inputdata _delegatorAddress = 0x5B38Da6a701c568545dCfcB03FcB875f56beddC4, _collectionAddress = 0x33FD426905F149f8376e227d0C9D3340AaD17aF1, _useCase = 50 and you will notice that the delegation was not registered.

Function | Use-Case  | Expected Output | Actual Output | Status
------------- | ------------- | ------------- | ------------- | -------------
registerDelegationAddress(...) | 50 | The delegation will not be registered as the execution of the transaction will fail. | The delegation was not registered. | Pass

### Test Case ID: 4

Test Case Objective: Register a delegation address on 0x33FD426905F149f8376e227d0C9D3340AaD17aF1 (The Memes by 6529 collection address) for the sub-delegation rights use case #16.\
\
***Prerequisite:***
1. Use case exists
2. Delegation Address is not locked
<!-- end of the list -->

***Input Data:***\
\
_collectionAddress = 0x33FD426905F149f8376e227d0C9D3340AaD17aF1\
_delegationAddress = 0xdD870fA1b7C4700F2BD7f44238821C26f7392148\
_expiryDate = 1682080764 (21/04/2023)\
_useCase = 16\
_allTokens = true\
_tokenid = 0

***Post-execution:***\
\
Call the retrieveDelegationAddresses(...) function with inputdata _delegatorAddress = 0x5B38Da6a701c568545dCfcB03FcB875f56beddC4, _collectionAddress = 0x33FD426905F149f8376e227d0C9D3340AaD17aF1, _useCase = 16 and the function will return the delegation address 0xdD870fA1b7C4700F2BD7f44238821C26f7392148.

Function | Use-Case  | Expected Output | Actual Output | Status
------------- | ------------- | ------------- | ------------- | -------------
registerDelegationAddress(...) | 16 | The delegation will be registered. | The delegation was not registered. | Pass

### Test Case ID: 5

Test Case Objective: Register a delegation address on 0x33FD426905F149f8376e227d0C9D3340AaD17aF1 (The Memes by 6529 collection address) for consolidation purposes use case #99.\
\
***Prerequisite:***
1. Use case exists
2. Delegation Address is not locked
<!-- end of the list -->

***Input Data:***\
\
_collectionAddress = 0x33FD426905F149f8376e227d0C9D3340AaD17aF1\
_delegationAddress = 0xdD870fA1b7C4700F2BD7f44238821C26f7392148\
_expiryDate = 1682080764 (21/04/2023)\
_useCase = 99\
_allTokens = true\
_tokenid = 0

***Post-execution:***\
\
Call the retrieveDelegationAddresses(...) function with inputdata _delegatorAddress = 0x5B38Da6a701c568545dCfcB03FcB875f56beddC4, _collectionAddress = 0x33FD426905F149f8376e227d0C9D3340AaD17aF1, _useCase = 99 and the function will return the delegation address 0xdD870fA1b7C4700F2BD7f44238821C26f7392148.

Function | Use-Case  | Expected Output | Actual Output | Status
------------- | ------------- | ------------- | ------------- | -------------
registerDelegationAddress(...) | 99 | The delegation will be registered. | The delegation was not registered. | Pass

<div id='revokeDelegationAddress'/>

## Revoke a delegation address from The Memes by 6529 collection.

### Description: In this group of test cases a wallet calls the revokeDelegationAddress(...) function to revoke a delegation address. Please make sure that the  address 0x5B38Da6a701c568545dCfcB03FcB875f56beddC4 is selected as an Account on remix and that you will revoke an address that was already registered for delegation.

### Test Case ID: 6

***Test Case Objective:*** \
\
Revoke a delegation address from 0x33FD426905F149f8376e227d0C9D3340AaD17aF1 (The Memes by 6529 collection address) that was already registered for the airdrop usecase #3.\
\
***Prerequisite:***
1. Execute Test Case ID 2.
2. Call the retrieveDelegationAddresses(...) function with inputdata _delegatorAddress = 0x5B38Da6a701c568545dCfcB03FcB875f56beddC4, _collectionAddress = 0x33FD426905F149f8376e227d0C9D3340AaD17aF1, _useCase = 3 and make sure that a delegation Address was registered for that specific use case. If you have already executed Test Case ID 2 you should be able to view as a result the delegation address 0xdD870fA1b7C4700F2BD7f44238821C26f7392148.
3. Usecase number exists 
4. Delegation Address was already registered
<!-- end of the list -->

***Input Data:***\
\
_collectionAddress = 0x33FD426905F149f8376e227d0C9D3340AaD17aF1\
_delegationAddress = 0xdD870fA1b7C4700F2BD7f44238821C26f7392148\
_useCase = 3

***Post-execution:***\
\
Call the retrieveDelegationAddresses(...) function with inputdata _delegatorAddress = 0x5B38Da6a701c568545dCfcB03FcB875f56beddC4, _collectionAddress = 0x33FD426905F149f8376e227d0C9D3340AaD17aF1, _useCase = 3, you will notice that the delegation address 0xdD870fA1b7C4700F2BD7f44238821C26f7392148 was revoked.

Function | Use-Case  | Expected Output | Actual Output | Status
------------- | ------------- | ------------- | ------------- | -------------
revokeDelegationAddress(...) | 3 | The delegation will be revoked. | The delegation was revoked. | Pass

<div id='updateDelegationAddress'/>

## Update a delegation address from The Memes by 6529 collection.

### Description: In this group of test cases a wallet calls the updateDelegationAddress(...) function to update a delegation address. Please make sure that the  address 0x5B38Da6a701c568545dCfcB03FcB875f56beddC4 is selected as an Account on remix and that you will update an address that was already registered for delegation.

### Test Case ID: 7

***Test Case Objective:*** \
\
Update a delegation address from 0x33FD426905F149f8376e227d0C9D3340AaD17aF1 (The Memes by 6529 collection address) that was already registered for all use cases #1.\
\
***Prerequisite:***
1. Execute Test Case ID 1.
2. Call the retrieveDelegationAddresses(...) function with inputdata _delegatorAddress = 0x5B38Da6a701c568545dCfcB03FcB875f56beddC4, _collectionAddress = 0x33FD426905F149f8376e227d0C9D3340AaD17aF1, _useCase = 1 and make sure that a delegation Address was registered for that specific use case. If you have already executed Test Case ID 1 you should be able to view as a result the delegation address 0xdD870fA1b7C4700F2BD7f44238821C26f7392148.
3. Usecase number exists 
4. Delegation Address was already registered
<!-- end of the list -->

***Input Data:***\
\
_collectionAddress = 0x33FD426905F149f8376e227d0C9D3340AaD17aF1\
_olddelegationAddress = 0xdD870fA1b7C4700F2BD7f44238821C26f7392148\
_newdelegationAddress = 0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2\
_expiryDate = 1682080764 (21/04/2023)\
_useCase = 1\
_allTokens = true\
_tokenid = 0

***Post-execution:***\
\
Call the retrieveDelegationAddresses(...) function with inputdata _delegatorAddress = 0x5B38Da6a701c568545dCfcB03FcB875f56beddC4, _collectionAddress = 0x33FD426905F149f8376e227d0C9D3340AaD17aF1, _useCase = 1 and the function will return the updated delegation address 0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2.

Function | Use-Case  | Expected Output | Actual Output | Status
------------- | ------------- | ------------- | ------------- | -------------
revokeDelegationAddress(...) | 1 | The delegation will be updated. | The delegation was updated. | Pass

<div id='registerDelegationAddressUsingSubDelegation'/>

## Register a delegation address for The Memes by 6529 collection using a wallet that has sub-delegation rights.

### Description: In this group of test cases a wallet calls the registerDelegationAddressUsingSubDelegation(...) function to register a delegation address on behalf of a Delegator that granted him/her sub-delegation rights. Firstly, please make sure that you run Test Case ID 4 and then make sure that the address 0xdD870fA1b7C4700F2BD7f44238821C26f7392148 is selected as an Account on remix.

### Test Case ID: 8

***Test Case Objective:*** \
\
Register a delegation address on behalf of a delegator on 0x33FD426905F149f8376e227d0C9D3340AaD17aF1 (The Memes by 6529 collection address) for minting use case #2.\
\
***Prerequisite:***
1. Execute Test Case ID 4.
2. Call the retrieveDelegationAddresses(...) function with inputdata _delegatorAddress = 0x5B38Da6a701c568545dCfcB03FcB875f56beddC4, _collectionAddress = 0x33FD426905F149f8376e227d0C9D3340AaD17aF1, _useCase = 16 and make sure that a delegation Address was registered for the sub-delegation usecase. If you have already executed Test Case ID 4 you should be able to view as a result the delegation address 0xdD870fA1b7C4700F2BD7f44238821C26f7392148.
3. Select the wallet address 0xdD870fA1b7C4700F2BD7f44238821C26f7392148 from accounts.
4. Usecase number exists.
5. Delegation Address in not locked.
<!-- end of the list -->

***Input Data:***\
\
_delegatorAddress = 0x5B38Da6a701c568545dCfcB03FcB875f56beddC4
_collectionAddress = 0x33FD426905F149f8376e227d0C9D3340AaD17aF1\
_delegationAddress = 0x4B0897b0513fdC7C541B6d9D7E929C4e5364D2dB\
_expiryDate = 1682080764 (21/04/2023)\
_useCase = 2\
_allTokens = true\
_tokenid = 0

***Post-execution:***\
\
Call the retrieveDelegationAddresses(...) function with inputdata _delegatorAddress = 0x5B38Da6a701c568545dCfcB03FcB875f56beddC4, _collectionAddress = 0x33FD426905F149f8376e227d0C9D3340AaD17aF1, _useCase = 2 and the function will return the updated delegation address 0x4B0897b0513fdC7C541B6d9D7E929C4e5364D2dB.

Function | Use-Case  | Expected Output | Actual Output | Status
------------- | ------------- | ------------- | ------------- | -------------
registerDelegationAddressUsingSubDelegation(...) | 2 | The delegation will be registered. | The delegation was registered. | Pass

<div id='revokeDelegationAddressUsingSubdelegation'/>

## Revoke a delegation address from The Memes by 6529 collection using a wallet that has sub-delegation rights.

### Description: In this group of test cases a wallet calls the revokeDelegationAddressUsingSubdelegation(...) function to revoke a delegation address on behalf of a Delegator that granted him/her sub-delegation rights. Firstly, execute Test Case ID 1. Secondly, please make sure that you executed Test Case ID 4 and then make sure that the address 0xdD870fA1b7C4700F2BD7f44238821C26f7392148 is selected as an Account on remix. 

### Test Case ID: 9

***Test Case Objective:*** \
\
Revoke a delegation address on behalf of a delegator on 0x33FD426905F149f8376e227d0C9D3340AaD17aF1 (The Memes by 6529 collection address) for all use cases #1.\
\
***Prerequisite:***
1. Execute Test Case ID 1.
2. Call the retrieveDelegationAddresses(...) function with inputdata _delegatorAddress = 0x5B38Da6a701c568545dCfcB03FcB875f56beddC4, _collectionAddress = 0x33FD426905F149f8376e227d0C9D3340AaD17aF1, _useCase = 1 and make sure that the function returns back delegation address 0xdD870fA1b7C4700F2BD7f44238821C26f7392148.
3. Execute Test Case ID 4.
4. Call the retrieveDelegationAddresses(...) function with inputdata _delegatorAddress = 0x5B38Da6a701c568545dCfcB03FcB875f56beddC4, _collectionAddress = 0x33FD426905F149f8376e227d0C9D3340AaD17aF1, _useCase = 16 and make sure that a delegation Address was registered for the sub-delegation usecase. If you have already executed Test Case ID 4 you should be able to view as a result the delegation address 0xdD870fA1b7C4700F2BD7f44238821C26f7392148.
5. Select the wallet address 0xdD870fA1b7C4700F2BD7f44238821C26f7392148 from accounts.
6. Usecase number exists.
<!-- end of the list -->

***Input Data:***\
\
_delegatorAddress = 0x5B38Da6a701c568545dCfcB03FcB875f56beddC4\
_collectionAddress = 0x33FD426905F149f8376e227d0C9D3340AaD17aF1\
_delegationAddress = 0xdD870fA1b7C4700F2BD7f44238821C26f7392148\
_useCase = 1

***Post-execution:***\
\
Call the retrieveDelegationAddresses(...) function with inputdata _delegatorAddress = 0x5B38Da6a701c568545dCfcB03FcB875f56beddC4, _collectionAddress = 0x33FD426905F149f8376e227d0C9D3340AaD17aF1, _useCase = 1, you will notice that the delegation address 0xdD870fA1b7C4700F2BD7f44238821C26f7392148 was revoked.

Function | Use-Case  | Expected Output | Actual Output | Status
------------- | ------------- | ------------- | ------------- | -------------
revokeDelegationAddressUsingSubdelegation(...) | 1 | The delegation will be revoked. | The delegation was revoked. | Pass
    
    
