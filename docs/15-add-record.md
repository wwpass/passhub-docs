---
sidebar_label: "Add new record"
sidebar_position: 15
---

# Add New Record

To add a new record, click the <img src={require('/img/AddButton.jpg').default} alt="Example banner" style={{boxShadow:"none", width:"30px", margin:"0 5px -5px"}}/> **Add** button. When you're on a mobile device, tap the safe name to get to the safe content and click the **Add** button. Select **Password**, **Note**, **File**, **Card** or **Folder** in the drop-down menu.

## New Password Record

Fill the form shown below, where

- _Title_ - identifies the account entry. It is the only required field in the form.
- _Username/password_ - the credentials of the account. Use the provided random password generator to get a strong password. Just click **Generate Password**.
- _URL_ - network name or IP address of the resource.
- _Notes_ - specific notes, instructions, or other messages are safely encrypted and stored with each entry.

![Password dialog](/img/passwordDialog.png)

### Google Authenticator (TOTP, Time-based One-Time Password)

You can add a second factor authenticator (rfc6238) to the login entry. The PassHub generates a six-digit sequence automatically for you. The one-time code generation is based on the shared secret (base32 string), which usually can be found close to the QR code on the service provider site, e.g.

![TOTP secret](/img/totpSecret.png)

In the Login Entry form click **Add Google Authenticator** secret to open the TOTP input field. Enter the shared secret code.

![Edit TOTP](/img/EditTotp.png)

Now the TOTP-code will be shown in the Login view along with time remaining till the code change:

![TOTP indicator](/img/totp.png)

## New Note

Note is a special type of record to store arbitrary not structured texts. The Note dialog contains only the _Title_ and the _Notes_ fields.

## New File

You can store files in PassHub too. These may be sensitive documents you share with clients or partners, SSL certificates used widely in IT, and so on. File names and content are encrypted the same way as all the other data in PassHub.

Click the **Browse** button to select a file, or, on a desktop, just drag the file into the filename filed. Optionally add notes. Later notes can help in search. Now click the Upload button.

![Upload File](/img/UploadFile.png)

:::note Upload multiple files

It is possible to upload multiple files in one step: just select files you need in the **Browse** dialog or Drag and Drop them on the desktop.

:::

## New Credit Card

Storing credit card data is quite straightforward: just put the credit card number, owner's name, CVV, and expiration date into the corresponding fields.

![Card Dialog](/img/card-dialog.png)

You can use PassHub.net browser extension to automatically fill in the card data on the payment page, e. g. when you shop online. For details, see the [Browser extension](https://passhub.net/doc/browser-extension) page.
