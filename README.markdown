# SnowMakerCore (.NET Core / .NET Standard version)
Originally created by [Tatham Oddie](https://github.com/tathamoddie) as [SnowMaker](https://github.com/tathamoddie/SnowMaker)

A high performance, distributed unique id generator for Azure environments.

Ids are longs, not ugly GUIDs.

This version updated by Chris Adol to use netcore2.0 / netstandard2.0 and async.

This version is available on NuGet as SnowMakerCore: [http://nuget.org/List/Packages/SnowMakerCore](http://nuget.org/List/Packages/SnowMakerCore)

Usage should be something like this (different to the original usage):
```csharp     
     var cloudStorageAccount = CloudStorageAccount.Parse(storageConnectionString);
     const string containerName = "snowmakerKeys";
     var dataStore = await BlobOptimisticDataStore.CreateAsync(cloudStorageAccount, containerName);
     var cloudyKeyGenerator = new UniqueIdGenerator(dataStore);
     var orderNumber = await cloudyKeyGenerator.NextIdAsync("orderNumbers");
```

This version is NOT affiliated to the original authors so please do not ask them for help with this version.

Documented at [http://blog.tatham.oddie.com.au/2011/07/14/released-snowmaker-a-unique-id-generator-for-azure-or-any-other-cloud-hosting-environment/](http://blog.tatham.oddie.com.au/2011/07/14/released-snowmaker-a-unique-id-generator-for-azure-or-any-other-cloud-hosting-environment/)

Heavily inspired by, and some code copied from [http://msdn.microsoft.com/en-us/magazine/gg309174.aspx](http://msdn.microsoft.com/en-us/magazine/gg309174.aspx)
