---
uid: General_Feature_Release_10.3.9_CU1
---

# General Feature Release 10.3.9 CU1 - Preview

> [!IMPORTANT]
> We are still working on this release. Some release notes may still be modified or moved to a later release. Check back soon for updates!

> [!IMPORTANT]
> When downgrading from DataMiner Feature Release version 10.3.8 (or higher) to DataMiner Feature Release version 10.3.4, 10.3.5, 10.3.6 or 10.3.7, an extra manual step has to be performed. For more information, see [Downgrading a DMS](xref:MOP_Downgrading_a_DMS).

> [!TIP]
>
> - For release notes related to DataMiner Cube, see [DataMiner Cube Feature Release 10.3.9](xref:Cube_Feature_Release_10.3.9).
> - For release notes related to the DataMiner web applications, see [DataMiner web apps Feature Release 10.3.9](xref:Web_apps_Feature_Release_10.3.9).
> - For information on how to upgrade DataMiner, see [Upgrading a DataMiner Agent](xref:Upgrading_a_DataMiner_Agent).

### Fixes

#### Cassandra backups would no longer work [ID_37217]

<!-- MR 10.4.0 - FR 10.3.9 [CU1] -->
<!-- Not added to MR 10.4.0 -->

DataMiner version 10.3.9 introduced additional binding redirects in the *CassandraBackup.exe.config* file. SLDataGateway would try to load these references, but as these were not available in the `C:\Skyline DataMiner\Tools` folder, this caused exceptions.

These references have now been removed again.