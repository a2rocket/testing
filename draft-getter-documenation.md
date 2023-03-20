# NFTDelegation Smart Contract Documenation
## Main Retrieve functions

[How to retrieve all delegation addresses delegated from a Delegator on a specific use case on a collection?](#retrieveDelegationAddresses)\
[How to retrieve all delegators who gave delegation rights to a delegation Address on a specific use case on a collection?](#retrieveDelegators)\
[How to check if a delegation exists given a delegator address?](#retrieveDelegatorStatusOfDelegation)\
[How to check if a delegation exists given a delegation address?](#retrieveDelegationAddressStatusOfDelegation)\
[How to retrieve the most recent delegation address delegated from a Delegator on a specific use case on a collection?](#retrieveMostRecentDelegation)\
[How to retrieve the most recent delegator who gave delegation rights to a delegation Address on a specific use case on a collection?](#retrieveMostRecentDelegator)\
[How to retrieve the active delegation addresses delegated from a Delegator on a specific use case on a collection?](#retrieveActiveDelegations)\
[How to retrieve the active delegators who gave delegation rights to a delegation Address on a specific use case on a collection?](#retrieveActiveDelegators)\


## Other Retrieve Functions

[How to retrieve all data about a delegator address for a specific usecase on a collection?](#retrieveDelegationAddressesTokensIDsandExpiredDates)\
[How to retrieve all data about a delegation address for a specific usecase on a collection?](#retrieveDelegatorsTokensIDsandExpiredDates)\
[How to retrieve the global lock status that exists on a delegation address?](#retrieveGloballockStatus)\
[How to retrieve the collection lock status that exists on a delegation address?](#retrieveCollectionLockStatus)\
[How to retrieve the collection use case lock status that exists on a delegation address?](#retrieveCollectionUseCaseLockStatus)\

## Main Retrieve functions

<div id='retrieveDelegationAddresses'/>

### How to retrieve all delegation addresses delegated from a Delegator on a specific use case on a collection?

<b>Purpose:</b> The retrieveDelegationAddresses() function retrieves all delegation addresses (active AND inactive) assigned by a delegator on a specific use case on a specific collection.

<b>Description:</b> The function takes three parameters: _delegatorAddress, _collectionAddress and _useCase. The _delegatorAddress parameter is the address of the delegator. The _collectionAddress parameter is the address of the collection for which the delegation addresses will be retrieved. The _useCase parameter is the type of delegation for which all delegation addresses will be returned. This function returns an address array that includes all delegation addresses delegated from a delegator on a specific usecase on a specific collection.

    /**
      * @dev Retrieve all delegation addresses delegated from a delegator.
      * @param _delegatorAddress The delegator address.
      * @param _collectionAddress The address of a specific collection.
      * @param _useCase The type of delegation.
      * @return an array with all delegation addresses.
    */
 
    function retrieveDelegationAddresses(
      address _delegatorAddress,
      address _collectionAddress,
      uint8 _useCase
    ) public view returns (address[]) {
      return delegationAddresses;
    }
    
<div id='retrieveDelegators'/>

### How to retrieve all delegators who gave delegation rights to a delegation Address on a specific use case on a collection?

<b>Purpose:</b> The retrieveDelegators() function retrieves all delegators addresses (active AND inactive) who gave delegation rights to a delegation Address on a specific use case on a specific NFT collection

<b>Description:</b> The function takes three parameters: _delegationAddress, _collectionAddress and _useCase. The _delegationAddress parameter is the address for which a delegator gave delegation rights. The _collectionAddress parameter is the address of the collection for which the delegators' addresses will be retrieved. The _useCase parameter is the type of delegation for which all delegators' addresses will be returned. This function returns an address array that includes all delegators' addresses who gave delegation rights to a delegation address on a specific usecase on a specific collection.

    /**
      * @dev Retrieve all delegators' addresses who gave delegation rights.
      * @param _delegationAddress The delegation address for which all delegators will be returned.
      * @param _collectionAddress The address of a specific collection.
      * @param _useCase The type of delegation.
      * @return an array with all delegators' addresses.
    */
 
    function retrieveDelegators(
      address _delegationAddress,
      address _collectionAddress,
      uint8 _useCase
    ) public view returns (address[]) {
      return delegatorsAddresses;
    }

<div id='retrieveDelegatorStatusOfDelegation'/>

### How to check if a delegation exists given a delegator address?

<b>Purpose:</b> The retrieveDelegatorStatusOfDelegation() function retrieves the status of a delegation given a delegator address.

<b>Description:</b> The function takes three parameters: _delegatorAddress, _collectionAddress and _useCase. The _delegatorAddress parameter is the address of the delegator. The _collectionAddress parameter is the address of the collection for which the status will be returned. The _useCase parameter is the type of delegation for which the delegation status will be returned. This function returns a boolean value indicating whether a delegation on a specific use case on a specific collection exists or not, if true it means that the delegator registered a delegation address on a specific use case on a specific collection.

    /**
      * @dev Retrieve the delegation status given a delegator address.
      * @param _delegatorAddress The delegator address.
      * @param _collectionAddress The address of a specific collection.
      * @param _useCase The type of delegation.
      * @return true if delegation exists, false otherwise.
    */
 
    function retrieveDelegatorStatusOfDelegation(
      address _delegatorAddress,
      address _collectionAddress,
      uint8 _useCase
    ) public view returns (bool) {
      return true/false;
    }

<div id='retrieveDelegationAddressStatusOfDelegation'/>

### How to check if a delegation exists given a delegation address?

<b>Purpose:</b> The retrieveDelegationAddressStatusOfDelegation() function retrieves the status of a delegation given a delegation address.

<b>Description:</b> The function takes three parameters: _delegationAddress, _collectionAddress and _useCase. The _delegationAddress parameter is the address for which this function checks if a delegation was registered. The _collectionAddress parameter is the address of the collection for which the status will be returned. The _useCase parameter is the type of delegation for which the delegation status will be returned. This function returns a boolean value indicating whether a delegation on a specific use case on a specific collection exists or not, if true it means that a delegator registered the given delegation address on a specific use case on a specific collection.

    /**
      * @dev Retrieve the delegation status given a delegation address.
      * @param _delegationAddress The delegation address.
      * @param _collectionAddress The address of a specific collection.
      * @param _useCase The type of delegation.
      * @return true if delegation exists, false otherwise.
    */
 
    function retrieveDelegationAddressStatusOfDelegation(
      address _delegationAddress,
      address _collectionAddress,
      uint8 _useCase
    ) public view returns (bool) {
      return true/false;
    }

<div id='retrieveMostRecentDelegation'/>

### How to retrieve the most recent delegation address delegated from a Delegator on a specific use case on a collection?

<b>Purpose:</b> The retrieveMostRecentDelegation() function retrieves the most recent delegation addresses assigned by a delegator on a specific use case on a specific collection.

<b>Description:</b> The function takes three parameters: _delegatorAddress, _collectionAddress and _useCase. The _delegatorAddress parameter is the address of the delegator. The _collectionAddress parameter is the address of the collection for which the most recent delegation address will be retrieved. The _useCase parameter is the type of delegation for which the most recent delegation address will be returned. This function returns the most recent address delegated from a delegator on a specific usecase on a specific collection.

    /**
      * @dev Retrieve the most recent delegation address delegated from a delegator.
      * @param _delegatorAddress The delegator address.
      * @param _collectionAddress The address of a specific collection.
      * @param _useCase The type of delegation.
      * @return the most recent delegation address.
    */
 
    function retrieveMostRecentDelegation(
      address _delegatorAddress,
      address _collectionAddress,
      uint8 _useCase
    ) public view returns (address) {
      return delegationAddress;
    }

<div id='retrieveMostRecentDelegator'/>

### How to retrieve the most recent delegator who gave delegation rights to a delegation Address on a specific use case on a collection?

<b>Purpose:</b> The retrieveMostRecentDelegator() function retrieves most recent delegator who gave delegation rights to a delegation Address on a specific use case on a specific NFT collection

<b>Description:</b> The function takes three parameters: _delegationAddress, _collectionAddress and _useCase. The _delegationAddress parameter is the address for which a delegator gave delegation rights. The _collectionAddress parameter is the address of the collection for which the delegators' addresses will be retrieved. The _useCase parameter is the type of delegation for which all delegators' addresses will be returned. This function returns the most recent delegator address who gave delegation rights to a delegation address on a specific usecase on a specific collection.

    /**
      * @dev Retrieve the most recent delegator address.
      * @param _delegationAddress The delegation address for which the most recent delegator will be returned.
      * @param _collectionAddress The address of a specific collection.
      * @param _useCase The type of delegation.
      * @return the most recent delegator address.
    */
 
    function retrieveMostRecentDelegator(
      address _delegationAddress,
      address _collectionAddress,
      uint8 _useCase
    ) public view returns (address) {
      return delegatorsAddress;
    }

<div id='retrieveActiveDelegations'/>

### How to retrieve the active delegation addresses delegated from a Delegator on a specific use case on a collection?

<b>Purpose:</b> The retrieveActiveDelegations() function retrieves the active delegation addresses assigned by a delegator on a specific use case on a specific collection.

<b>Description:</b> The function takes four parameters: _delegatorAddress, _collectionAddress, _date and _useCase. The _delegatorAddress parameter is the address of the delegator. The _collectionAddress parameter is the address of the collection for which the active delegation addresses will be retrieved. The _date parameter is the epoch time value for which the active delegation addresses will be retrieved, _date compares its value against the _expiryDate that was given when a delegation was registered. The _useCase parameter is the type of delegation for which all delegation addresses will be returned. This function returns an address array that includes the active delegation addresses delegated from a delegator on a specific usecase on a specific collection.

    /**
      * @dev Retrieve the active delegation addresses delegated from a delegator.
      * @param _delegatorAddress The delegator address.
      * @param _collectionAddress The address of a specific collection.
      * @param _date The epoch time value of a given date.
      * @param _useCase The type of delegation.
      * @return an array with all delegation addresses.
    */
 
    function retrieveActiveDelegations(
      address _delegatorAddress,
      address _collectionAddress,
      uint256 _date,
      uint8 _useCase
    ) public view returns (address[]) {
      return delegationAddresses;
    }

<div id='retrieveActiveDelegators'/>

### How to retrieve the active delegators who gave delegation rights to a delegation Address on a specific use case on a collection?

<b>Purpose:</b> The retrieveActiveDelegators() function retrieves the active delegators addresses who gave delegation rights to a delegation Address on a specific use case on a specific NFT collection

<b>Description:</b> The function takes four parameters: _delegationAddress, _collectionAddress, _date and _useCase. The _delegationAddress parameter is the address for which a delegator gave delegation rights. The _collectionAddress parameter is the address of the collection for which the delegators' addresses will be retrieved. The _date parameter is the epoch time value for which the active delegators' addresses will be retrieved, _date compares its value against the _expiryDate that was given when a delegation was registered. The _useCase parameter is the type of delegation for which all delegators' addresses will be returned. This function returns an address array that includes the active delegators' addresses who gave delegation rights to a delegation address on a specific usecase on a specific collection.

    /**
      * @dev Retrieve the active delegators' addresses who gave delegation rights.
      * @param _delegationAddress The delegation address for which all delegators will be returned.
      * @param _collectionAddress The address of a specific collection.
      * @param _date The epoch time value of a given date.
      * @param _useCase The type of delegation.
      * @return an array with all delegators' addresses.
    */
 
    function retrieveActiveDelegators(
      address _delegationAddress,
      address _collectionAddress,
      uint256 _date,
      uint8 _useCase
    ) public view returns (address[]) {
      return delegatorsAddresses;
    }

## Other Retrieve Functions

<div id='retrieveDelegationAddressesTokensIDsandExpiredDates'/>

### How to retrieve all data about a delegator address for a specific usecase on a collection?

<b>Purpose:</b> The retrieveDelegationAddressesTokensIDsandExpiredDates() function retrieves for a specific use case on a specific collection, the delegation addresses, token IDs, expiry dates and if the delegator assigned all tokens owned or a specific token when codnucting a delegation.

<b>Description:</b> The function takes three parameters: _delegatorAddress, _collectionAddress and _useCase. The _delegatorAddress parameter is the address of the delegator. The _collectionAddress parameter is the address of the collection for which full data will be retrieved. The _useCase parameter is the type of delegation for which full data will be returned. This function returns an address array that includes all delegation addresses delegated from a delegator on a specific usecase on a specific collection, a uint array that includes the token ids that were registered, a bool array that indicates if all tokens owned by the delegator were assigned during the registration or just a specific token id and a uint array that includes expiry dates of each delegation.

    /**
      * @dev Retrieve full data about a delegator.
      * @param _delegatorAddress The delegator address for which full data will be returned.
      * @param _collectionAddress The address of a specific collection.
      * @param _useCase The type of delegation.
      * @return an array with all delegation addresses, an array with the token ids registered, an array that indicates if the delegator delegated all tokens owned or a specific token and an array with the expiry dates of each delegation.
    */
 
    function retrieveDelegationAddressesTokensIDsandExpiredDates(
      address _delegatorAddress,
      address _collectionAddress,
      uint8 _useCase
    ) public view returns (address[]) {
      return delegationAddresses, tokenIDs, allTokens, allExpirations;
    }
    
<div id='retrieveDelegatorsTokensIDsandExpiredDates'/>

### How to retrieve all data about a delegation address for a specific usecase on a collection?

<b>Purpose:</b> The retrieveDelegatorsTokensIDsandExpiredDates() function retrieves for a specific use case on a specific collection, the delegators' addresses, token IDs, expiry dates and if the delegator assigned all tokens owned or a specific token when codnucting a delegation.

<b>Description:</b> The function takes three parameters: _delegationAddress, _collectionAddress and _useCase. The _delegationAddress parameter is the address for which full data will be retrieved. The _collectionAddress parameter is the address of the collection for which full data will be retrieved. The _useCase parameter is the type of delegation for which full data will be returned. This function returns an address array that includes all delegators' addresses who gave delegation rights to a delegation address on a specific usecase on a specific collection, a uint array that includes the token ids that were registered, a bool array that indicates if all tokens owned by the delegator were assigned during the registration or just a specific token id and a uint array that includes expiry dates of each delegation.

    /**
      * @dev Retrieve full data about a delegation address.
      * @param _delegationAddress The delegation address for which full data will be returned.
      * @param _collectionAddress The address of a specific collection.
      * @param _useCase The type of delegation.
      * @return an array with all delegators' addresses, an array with the token ids registered, an array that indicates if the delegator delegated all tokens owned or a specific token and an array with the expiry dates of each delegation.
    */
 
    function retrieveDelegatorsTokensIDsandExpiredDates(
      address _delegationAddress,
      address _collectionAddress,
      uint8 _useCase
    ) public view returns (address[]) {
      return delegatorsAddresses, tokenIDs, allTokens, allExpirations;
    }
    
<div id='retrieveGloballockStatus'/>

### How to retrieve the global lock status that exists on a delegation address?

<b>Purpose:</b> The retrieveGloballockStatus() function retrieves the global lock status of a delegation Address.

<b>Description:</b> The function takes one parameter: _delegationAddress. The _delegationAddress parameter is the address for which the global lock status will be returned. This function returns a boolean value indicating whether the global lock is enabled or not, if true it means that the _delegationAddress is locked and cannot be registered in any other usecase or collection.

    /**
      * @dev Retrieve the global lock status of a delegation address.
      * @param _delegationAddress The delegation address.
      * @return true if the global lock is enabled, false otherwise.
    */
 
    function retrieveGloballockStatus(
      address _delegationAddress
    ) public view returns (bool) {
      return globalLock;
    }

<div id='retrieveCollectionLockStatus'/>

### How to retrieve the collection lock status that exists on a delegation address?

<b>Purpose:</b> The retrieveCollectionLockStatus() function retrieves the collection lock status of a delegation Address.

<b>Description:</b> The function takes two parameters: _collectionAddress and _delegationAddress. The _collectionAddress parameter is the address of the collection for which the collection lock status of a delegation Address will be retrieved. The _delegationAddress parameter is the address for which the collection lock status will be returned. This function returns a boolean value indicating whether the collection lock is enabled or not, if true it means that the _delegationAddress is locked and cannot be registered within the same collection.

    /**
      * @dev Retrieve the collection lock status of a delegation address.
      * @param _collectionAddress The address of a specific collection.
      * @param _delegationAddress The delegation address.
      * @return true if the collection lock is enabled, false otherwise.
    */
 
    function retrieveCollectionLockStatus(
      address _collectionAddress,
      address _delegationAddress
    ) public view returns (bool) {
      return collectionLock;
    }

<div id='retrieveCollectionUseCaseLockStatus'/>

### How to retrieve the collection use case lock status that exists on a delegation address?

<b>Purpose:</b> The retrieveCollectionUseCaseLockStatus() function retrieves the collection use case lock status of a delegation Address.

<b>Description:</b> The function takes three parameters: _collectionAddress, _delegationAddress and _useCase. The _collectionAddress parameter is the address of the collection for which the collection use case lock status of a delegation Address will be retrieved. The _delegationAddress parameter is the address for which the collection use case lock status will be returned. The _useCase parameter is the type of delegation for which the collection use case status will be returned. This function returns a boolean value indicating whether the collection use case lock is enabled or not, if true it means that the _delegationAddress is locked and cannot be registered for the same use case within the same collection.

    /**
      * @dev Retrieve the collection use case lock status of a delegation address.
      * @param _collectionAddress The address of a specific collection.
      * @param _delegationAddress The delegation address.
      * @param _useCase The type of delegation.
      * @return true if the collection lock is enabled, false otherwise.
    */
 
    function retrieveCollectionUseCaseLockStatus(
      address _collectionAddress,
      address _delegationAddress,
      uint8 _useCase
    ) public view returns (bool) {
      return collectionUsecaseLock;
    }




