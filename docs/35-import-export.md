---
sidebar_label: "Import / Export"
sidebar_position: 35
---

# Backup and Restore My Records

You can export your records in XML or CSV file and import them later.

## Export and Backup

- Export all safes (backup): select **Export** in the Account drop-down.
- Export a single safe: click **Export** item in the safe menu.

In the provided dialog, choose one of the two file formats - XML or CSV. For backup/restore purposes, _XML is highly recommended_. Use CSV only for compatibility reasons or to get the exported data in a human-readable form e.g. to put them into an Excel table. CSV is error-prone, does not preserve real data structures, and suffers compatibility issues.

![Export dialog](/img/ExportDialog.png)

### Compatibility With KeePass

There are many KeePass flavors, particularly:

- KeePass 2 - for Windows
- Keepass2Android - for Android devices
- KeepassXC - cross-platform application for MAC, Linux, and Windows

Windows and Android versions support the XML format as a primary choice. CSV implementation contains errors and is not recommended. Cross-platform KeePassXC supports CSV only, and this implementation is correct.

SUMMARY: use CSV for KeePassXC and XML for KeePass2/Windows and KeePass2Andoird

## Import and Restore

Select **Import** in the Account drop-down

![Import item](/img/Import.png)

Select mode: _Import_ (puts file data into a newly created single safe) or _Restore_ (merges file data with existing safes)
Select the file you wish to upload

![Import dialog](/img/ImportDialog.png)

NOTE: Restore mode preserves all the data you have in PassHub, it can only add new records or additional versions of existing records. It never deletes or modifies the existing data.
