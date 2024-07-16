---
sidebar_label: "Import / Export"
sidebar_position: 35
---

# Backup and Restore My Records

You can export your records in XML or CSV format and import them later.

## Export and Backup

- Export all safes (backup): select **Export** in the Account drop-down menu.
- Export a single safe: click **Export** in the safe's menu.

In either dialog, choose one of the two file formats - XML or CSV. For backup/restore purposes, _XML is highly recommended_. Use CSV only for compatibility reasons or to get the exported data in a human-readable form (e.g. to put them into an Excel table). CSV is error-prone, does not preserve real data structures, and suffers many compatibility issues.

![Export dialog](/img/ExportDialog.png)

### Compatibility With KeePass

There are many KeePass flavors, particularly:

- KeePass 2 - for Windows
- KeePass2Android - for Android devices
- KeePassXC - cross-platform application for MAC, Linux, and Windows

Windows and Android versions support the XML format as a primary choice; using CSV format on these versions is more error-prone. Cross-platform KeePassXC supports CSV only, and this implementation is correct.

:::note Summary
Use CSV for KeePassXC, and XML for KeePass2/Windows and KeePass2Android.
:::

## Import and Restore

Select **Import** in the Account drop-down menu.

![Import item](/img/Import.png)

Select a mode: _Import_ (puts file data into a newly created single safe) or _Restore_ (merges file data with existing safes). Then select the file you wish to upload.

![Import dialog](/img/ImportDialog.png)

NOTE: Restore mode preserves all the data you have in PassHub. It can only add new records or additional versions of existing records; it never deletes or modifies existing data.
