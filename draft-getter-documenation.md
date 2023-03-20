# NFTDelegation Smart Contract Documenation
## Getter/Retrieve functions
[How to retrieve the global lock status that exists on a delegation address?](#retrieveGloballockStatus)\
[How to retrieve the collection lock status that exists on a delegation address?](#retrieveCollectionLockStatus)\
[How to retrieve the collection use case lock status that exists on a delegation address?](#retrieveCollectionUseCaseLockStatus)\

<div id='retrieveGloballockStatus'/>

### How to retrieve the global lock status that exists on a delegation address?

<b>Purpose:</b> The retrieveGloballockStatus() function retrieves the global lock status of a delegation Address.

<b>Description:</b> The function takes one parameter: _delegationAddress. The _delegationAddress parameter is the address for which the global lock status will be returned. It returns a boolean value indicating whether the global lock is enabled or not, if true it means that the _delegationAddress is locked and cannot be registered in any other usecase or collection.

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

<b>Description:</b> The function takes two parameters: _collectionAddress and _delegationAddress. The _collectionAddress parameter is the address of the collection for which the collection lock status of a delegation Address will be retrieved. The _delegationAddress parameter is the address for which the collection lock status will be returned. It returns a boolean value indicating whether the collection lock is enabled or not, if true it means that the _delegationAddress is locked and cannot be registered within the same collection.

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

<b>Description:</b> The function takes three parameters: _collectionAddress, _delegationAddress and _useCase. The _collectionAddress parameter is the address of the collection for which the collection use case lock status of a delegation Address will be retrieved. The _delegationAddress parameter is the address for which the collection use case lock status will be returned. It returns a boolean value indicating whether the collection use case lock is enabled or not, if true it means that the _delegationAddress is locked and cannot be registered for the same use case within the same collection.

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




