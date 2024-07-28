---
sidebar_label: "LastPass to PassHub migration"
sidebar_position: 55
---

# How to migrate from LastPass to PassHub.net

_Step-by-step instructions_

To migrate your data from your LastPass account to PassHub.net, follow the four steps below:

1. Create a Passhub.net account if you do not have one.
2. Export your LastPass records to a CSV file.
3. On the Passhub.net page, import the CSV file to the new safe.
4. Delete the CSV file on your computer.

## Export LastPass Data

Open the LastPass extension popup and log in to your account. Click the LastPass Extension icon in the upper right corner of the browser window. Select the Account Settings (the item at the bottom with your email address).

![LastPass extension](/img/migration/lp1a.png)

Select the **Advanced** submenu.

![Advanced Submenu](/img/migration/lp2a.png)

Choose **Export**.

![Export Item](/img/migration/lp3a.png)

Now click **LastPass CSV file**.

![LP CSV File](/img/migration/lp4a.png)

You may be asked to provide your LastPass master password.

![LP master password](/img/migration/lp5.png)

Browser exports data to a **lastpass_export.csv** file (by default in the Downloads directory).

![LP export CSV](/img/migration/lp6a.png)

## Import Data to a New PassHub Safe

Now open PassHub.net and click the Import link.

![PassHub import link](/img/ImportLink.png)

With the **Browse** button, select the **lastpass_export.csv** file. PassHub detects LastPass files automatically. Be sure to import the data into a new safe.

![MigrationImportDialog](/img/MigrationImportDialog.png)

PassHub creates a new safe with the LastPass folder in it.

![PassHub import](/img/LastPassImported.png)

## Delete lastpass_export.csv

Now that your data is safely stored in PassHub.net, we highly recommend you delete the **lastpass_export.csv** file, as it contains unencrypted sensitive data.
