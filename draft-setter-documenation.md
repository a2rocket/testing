# NFTDelegation Smart Contract Documenation
## Setter functions
[registerDelegationAddress](#registerDelegationAddress)  
[registerDelegationAddressUsingSubDelegation](#registerDelegationAddressUsingSubDelegation)\
[revokeDelegationAddress](#revokeDelegationAddress)\
[revokeDelegationAddressUsingSubdelegation](#revokeDelegationAddressUsingSubdelegation)\
[batchDelegations](#batchDelegations)\
[batchRevocations](#batchRevocations)\
[updateDelegationAddress](#updateDelegationAddress)\
[setglobalLock](#setglobalLock)\
[setcollectionLock](#setcollectionLock)\
[setcollectionUsecaseLock](#setcollectionUsecaseLock)

### registerDelegationAddress()

<b>Purpose:</b> The registerDelegationAddress() function registers a new delegation Address.

<b>Description:</b> The function takes six parameters: _collectionAddress, _delegationAddress, _expiryDate, _useCase, _allTokens and _tokenid. The _collectionAddress parameter is the address of the collection that the delegation address will be registered. The _delegationAddress parameter is the address to register. The _expiryDate parameter sets the expiry date of the delegation, after that date the delegation is not active. The _useCase parameter is the type of delegation to register. The _allTokens parameter can take two statuses (true/false), if true it registers the delegation for all collection tokens owned by the delegator, if false then it refers to a specific token that is set on the _tokenid parameter. The _tokenid parameter is the ID of the token to register the delegation for.

<b>Notes:</b> 
  * To register a delegation Address for all collections the value of parameter _collectionAddress should be set to 0x8888888888888888888888888888888888888888.
  * To delegate for all tokens owned set the _allTokens parameter to true, otherwise, by setting _allTokens to false the delegation refers only to the token id set in the _tokenid parameter

<!-- end of the list -->

    /**
      * @dev Registers a new delegation address.
      * @param _collectionAddress The address of a specific collection.
      * @param _delegationAddress The delegation address.
      * @param _expiryDate The expiry date of the delegation.
      * @param _useCase The type of delegation.
      * @param _allTokens Refers to all tokens owned by a delegator or a specific token.
      * @param _tokenid The ID of the token to register the delegation for. 
    */
 
    function registerDelegationAddress(
      address _collectionAddress,
      address _delegationAddress,
      uint256 _expiryDate,
      uint8 _useCase
      bool _allTokens,
      uint256 _tokenid
    ) public;
 
### registerDelegationAddressUsingSubDelegation() 

<b>Purpose:</b> The registerDelegationAddressUsingSubDelegation() function registers a new delegation Address by taking into consideration the sub-delegation rights given by a delegator to a specific delegation Address.

<b>Description:</b> The function takes seven parameters: _delegatorAddress, _collectionAddress, _delegationAddress, _expiryDate, _useCase, _allTokens and _tokenid. The _delegatorAddress parameter is the address of the delegator who gave sub-delegation rights to the address that will execute this function. The _collectionAddress parameter is the address of the collection that the delegation will be registered. The _delegationAddress parameter is the address to register. The _expiryDate parameter sets the expiry date of the delegation, after that date the delegation is not active. The _useCase parameter is the type of delegation to register. The _allTokens parameter can take two status (true/false), if true it registers the delegation for all collection tokens owned by the delegator, if false then it refers to a specific token that is set on the _tokenid parameter. The _tokenid parameter is the ID of the token to register the delegation for. 

    /**
      * @dev Registers a new delegation address from a hot wallet that has sub-delegation rights.
      * @param _delegatorAddress The address of the delegator who gave sub-delegation rights.
      * @param _collectionAddress The address of a specific collection.
      * @param _delegationAddress The delegation address.
      * @param _expiryDate The expiry date of the delegation.
      * @param _useCase The type of delegation.
      * @param _allTokens Refers to all tokens owned by a delegator or a specific token.
      * @param _tokenid The ID of the token to register the delegation for. 
     */

    function registerDelegationAddressUsingSubDelegation(
        address _ delegatorAddress,
        address _collectionAddress,
        address _delegationAddress,
        uint256 _expiryDate,
        uint8 _useCase
        bool _allTokens,
        uint256 _tokenid
    ) public;
 
### revokeDelegationAddress() 

<b>Purpose:</b> The revokeDelegationAddress() function revokes the delegation rights given to a delegation address on a specific use case for a specific NFT collection.

<b>Description:</b> The function takes three parameters: _collectionAddress, _delegationAddress and _useCase. The _collectionAddress parameter is the address of the collection that the delegation will be revoked. The _delegationAddress parameter is the address that will be revoked. The _useCase parameter is the type of delegation that will be revoked. 

      /**
        * @dev Revokes a delegation address.
        * @param _collectionAddress The address of a specific collection.
        * @param _delegationAddress The delegation address.
        * @param _expiryDate The expiry date of the delegation.
        * @param _useCase The type of delegation.
      */

      function revokeDelegationAddress(
          address _collectionAddress,
          address _delegationAddress,
          uint8 _useCase
      ) public;
 
### revokeDelegationAddressUsingSubdelegation() 

<b>Purpose:</b> The revokeDelegationAddressUsingSubdelegation() function revokes the delegation rights given to a delegation address on a specific use case for a specific NFT collection by taking into consideration the sub-delegation rights given by a delegator to a specific delegation Address.

<b>Description:</b> The function takes four parameters: _delegatorAddress, _collectionAddress, _delegationAddress and _useCase. The _delegatorAddress parameter is the address of the delegator who gave sub-delegation rights to the address that will execute this function. The _collectionAddress parameter is the address of the collection that the delegation will be revoked. The _delegationAddress parameter is the address that will be revoked. The _useCase parameter is the type of delegation that will be revoked. 

      /**
        * @dev Revokes a delegation address from a delegator using sub-delegation rights.
        * @param _delegatorAddress The address of the delegator who gave sub-delegation rights.
        * @param _collectionAddress The address of a specific collection.
        * @param _delegationAddress The delegation address.
        * @param _useCase The type of delegation.
      */

      function revokeDelegationAddress(
          address _delegatorAddress,
          address _collectionAddress,
          address _delegationAddress,
          uint8 _useCase
      ) public;
      
### batchDelegations() 

<b>Purpose:</b> The batchDelegations() function registers delegation rights to 1..5 delegation addresses on various use cases of different NFT collections.

<b>Description:</b> The function takes six parameters:  _collectionAddresses[], _delegationAddresses[], _expiryDates[], _useCases[], _allTokens[] and _tokenids[]. The _collectionAddresses[] parameter is an array that includes the collection addresses for each one of the delegation addresses that will be registered. The _delegationAddresses[] parameter is an array that includes the delegation addresses that will be registered for each one of the collection addresses. The _expiryDates[] parameter is an array that includes the expiry date for each one of the delegations. The _useCases[] parameter is an array that includes the type of a delegation that will be registered. The _allTokens parameter is an array that refers to the delegated tokens of each collection. The _tokenids[] parameter is an array that specifies the token id assigned to a delegation.

      /**
        * @dev Registers 1..5 delegation addresses to a delegator.
        * @param _collectionAddresses[] The addresses of specific collections.
        * @param _delegationAddresses[] The delegation addresses.
        * @param _expiryDates[] The expiry date of each delegation.
        * @param _useCases[] The type of each delegation.
        * @param _allTokens[] Refers to all tokens owned by a delegator or a specific token.
        * @param _tokenids[] The ID of the token to register the delegation for. 
      */

      function batchDelegations(
          address[] _ collectionAddresses,
          address[] _ delegationAddresses,
          uint256[] _ expiryDates,
          uint8[] _useCases,
          bool[] _allTokens,
          uint256[] _tokenids
      ) public;
 
### batchRevocations() 

<b>Purpose:</b> The batchRevocations() function revokes the delegation rights given to 1..5 delegation addresses on various use cases of different NFT collections.

<b>Description:</b> The function takes three parameters:  _collectionAddresses[], _delegationAddresses[] and _useCases[]. The _collectionAddresses parameter is an array that includes the collection addresses for each one of the delegation addresses that will be revoked. The _delegationAddresses parameter is an array that includes the delegation addresses for each one of the collection addresses that will be revoked. The _useCases parameter is an array that includes the types of delegations that will be revoked. 

      /**
        * @dev Revokes 1..5 delegation addresses from a delegator.
        * @param _collectionAddresses[] The addresses of specific collections.
        * @param _delegationAddresses[] The delegation addresses.
        * @param _ useCases[] The types of delegations.
      */

      function batchRevocations(
          address[] _ collectionAddresses,
          address[] _ delegationAddresses,
          uint8[] _ useCases
      ) public;

### updateDelegationAddress() 

<b>Purpose:</b> The updateDelegationAddress() function updates a delegation Address.

<b>Description:</b> The function takes seven parameters: _collectionAddress, _olddelegationAddress, _newdelegationAddress, _expiryDate, _useCase, _allTokens and _tokenid. The _collectionAddress parameter is the address of the collection that the new delegation will be registered. The _olddelegationAddress parameter is the address that will be removed.  The _newdelegationAddress parameter is the address to register. The _expiryDate parameter sets the expiry date of the delegation, after that date the delegation is not active. The _useCase parameter is the type of delegation to register. The _allTokens parameter can take two statuses (true/false), if true it registers the delegation for all collection tokens owned by the delegator, otherwise, if false then it refers to a specific token that is set on the _tokenid parameter. The _tokenid parameter is the ID of the token to register the delegation for. 

      /**
        * @dev Updates a delegation address.
        * @param _collectionAddress The address of a specific collection.
        * @param _newdelegationAddress The previous delegation address.
        * @param _newdelegationAddress The new delegation address.
        * @param _expiryDate The expiry date of the delegation.
        * @param _useCase The type of delegation.
        * @param _allTokens Refers to all tokens owned by a delegator or a specific token.
        * @param _tokenid The ID of the token to register the new delegation for.
      */

      function updateDelegationAddress(
          address _collectionAddress,
          address _olddelegationAddress,
          address _newdelegationAddress,
          uint256 _expiryDate,
          uint8 _useCase
          bool _allTokens,
          uint256 _tokenid
      ) public;
 
### setglobalLock() 

<b>Purpose:</b> The setglobalLock() function locks the wallet address that executes the transaction to prevent any delegation registration of it on any use case on any collection.

<b>Description:</b> The function takes one parameter:  _status. The _status parameter is a bool value (true/false), if _status = true the wallet address locks itself, if _status = false the wallet address unlocks.

      /**
        * @dev Locks a wallet address globally.
        * @param _status The lock status of the wallet address.
      */

      function setglobalLock(
          bool _status
      ) public;

 
### setcollectionLock() 

<b>Purpose:</b> The setcollectionLock() function locks the wallet address that executes the transaction to prevent any registration of it on a specific collection.

<b>Description:</b> The function takes two parameters:  _collectionAddress and _status. The _collectionAddress parameter is the address of the collection that the wallet address will be locked/unlocked. The _status parameter is a bool value (true/false), if _status = true the wallet address locks itself, if _status = false the wallet address unlocks.

      /**
        * @dev Locks a wallet address on a specific collection.
        * @param _collectionAddress The address of a specific collection.
        * @param _status The lock status of the wallet address.
      */

      function setcollectionLock(
          address _collectionAddress,
          bool _status
      ) public;
 
### setcollectionUsecaseLock() 

<b>Purpose:</b> The setcollectionUsecaseLock () function locks the wallet address that executes the transaction to prevent any registration of it on a specific usecase on a specific collection.

<b>Description:</b> The function takes three parameters:  _collectionAddress, _useCase and _status. The _collectionAddress parameter is the address of the collection that the wallet address will be locked/unlocked. The _useCase parameter is the type for which the wallet address will be locked/unlocked. The _status parameter is a bool value (true/false), if _status = true the wallet address locks itself, if _status = false the wallet address unlocks.

      /**
        * @dev Locks a wallet address on a specific usecase on a specific collection.
        * @param _collectionAddress The address of a specific collection.
        * @param _useCase The type for which the wallet address will be locked/unlocked.
        * @param _status The lock status of the wallet address.
      */

      function setcollectionUsecaseLock(
          address _collectionAddress,
          uint8 _useCase,
          bool _status
      ) public;
