---
sidebar_label: "Add new record"
sidebar_position: 15
---

# Add New Record

Tap or click on a safe's name to get to its contents, then click the <img src={require('/img/AddButton.jpg').default} alt="Example banner" style={{boxShadow:"none", width:"30px", margin:"0 5px -5px"}}/> **Add** button. Select **Password**, **Note**, **File**, **Card** or **Folder** in the drop-down menu.

## New Password Record

Fill the form shown below, where

- _Title_ - identifies the account entry. It is the only required field in the form.
- _Username/password_ - the credentials of the account. Use the provided random password generator to get a strong password by simply clicking **Generate Password**.
- _URL_ - network name or IP address of the resource.
- _Notes_ - specific notes, instructions, or any other messages you want to include. These are safely encrypted and stored with each entry.

![Password dialog](/img/passwordDialog.png)

### Google Authenticator (TOTP, Time-based One-Time Password)

You can add a _second factor authenticator_ (rfc6238) to the login entry. PassHub generates a six-digit sequence automatically for you. The one-time code generation is based on a _shared secret_ (base32 string), which usually can be found close to the QR code on the service provider site, e.g.

![TOTP secret](/img/totpSecret.png)

In the Login Entry form, click **Add Google Authenticator** secret to open the TOTP input field. Enter the shared secret code.

![Edit TOTP](/img/EditTotp.png)

Now the TOTP-code will be shown in the Login view, alongside a timer indicating when the code will change:

![TOTP indicator](/img/totp.png)

## New Note

Note is a special type of record to store arbitrary, unstructured texts. The Note dialog contains only the _Title_ and the _Notes_ fields.

## New File

You can store files in PassHub, too! These may be sensitive documents you share with clients, SSL certificates used widely in IT, and so on. File names and content are encrypted the same way as all the other data in PassHub.

Click the **Browse** button to select a file, or, on a desktop, just drag the file into the filename field. You can also add a note, which can help you search for this file in the future.

When finished, click the Upload button.

![Upload File](/img/UploadFile.png)

:::note Upload multiple files

You can upload multiple files at once: just what you need in the **Browse** dialog, or Drag and Drop them on desktop.

:::

## New Credit Card

Storing credit card data is straightforward: just enter the credit card number, owner's name, CVV, and expiration date into the corresponding fields.

![Card Dialog](/img/card-dialog.png)

You can use the PassHub.net browser extension to automatically fill in your card data when you shop online. For details, see the [Browser extension](https://passhub.net/doc/browser-extension) page.
