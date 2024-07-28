---
sidebar_label: "PassHub for Business"
sidebar_position: 70
---

# PassHub for Business

## Self-Hosted PassHub

PassHub is an open-source project with the code available on GitHub. See https://github.com/wwpass/passhub for the backend and https://github.com/wwpass/passhub-frontend for the frontend.

You can deploy an instance of PassHub on your company servers, either via VPS or hardware located in a data center. This way you have full control of your data.

Follow the [installation instructions](https://github.com/wwpass/passhub/blob/master/InstallingPassHubOnUbuntu20.04.md) for Ubuntu servers.
The PassHub architecture can fit the service on a single host or on three hosts with replicated database and a few web servers. It is possible to bind the PassHub to the company's Active Directory for uniform user rights control. Alternatively, you may use the built-in user control feature of PassHub for Business, [see below](/doc/passhub-business#passhub-user-management).

## PassHub as a Service

An easier way to get the PassHub instance and control user access to you company data is to subscribe to PassHub as a service. We deploy a PassHub server with a URL yourcompany.passhub.us in the US, or yourcompany.passhub.us in the EU. To start, you provide the email of the first user who will be assigned an administrator role.


## PassHub user management

As an administrator, sign in to PassHub. See https://passhub.net/doc/ for details.

Scan the QR code on your PassHub site with WWPass Key. During this first sign-in, you will be asked to confirm the email.
When your account is created, you are automatically assigned the site administrator role.
Same as other users, you can create your own records, safes, and share them with your colleagues. Being the site administrator, you can also add PassHub users, change their access rights, and revoke or temporarily disable user access.

To get to the user management page, click the "Account" icon in the upper right corner of PassHub page and select "Users" item with the wrench icon.

![IAM menu item](/img/iam_menu_item1.png)

On the user management page, you can invite/authorize a new user to create an account with their email address. 

Use "status" column to control the user status: 

- Admin: site administrator
- Disabled: temporarily revoke user access
- Active: normal user


You can also delete the user account, but this operation is one-way: any unshared user data will be completely lost. The disable operation is safe and reversible. 


![User Table](/img/user_table.jpg)


## User groups

Groups represent a widely used technique to provide access rights to users depending on their department, role, etc. in an organization. PassHub allows site admins to create user groups, add users to the group, and define a list of safes along with access rights to particular safes ("edit" or "view-only").

Only site administrators are allowed to access Group management controls. Here is how it's done:

### Step 1. Create a new group

On the "User page", click the "Add Group" button in the "User Groups" pane.
Select a unique name for the group. 

![Create Group](/img/create_group.jpg)


### Step 2. Add users to the group

Click on a group record. Choose "Users" in the group menu.


![User Group Menu](/img/user_groups_menu.jpg)  

"Select user to add" shows a list of users you can include in the group. 

NOTE:  invited (authorized) users are not listed if they have not created a PassHub account yet (i.e., are not in an active, admin, etc. state).

![Add User Group Members](/img/user_groups_members.jpg)


The "Add" button puts the selected user into the group list. Later, you can remove any user by clicking the "X" icon in the corresponding line. You, being a site admin and the creator of the group, are also a member of the group.

![User Group Members](/img/user_groups_members2.jpg)

Use the red cross icon to the left of the user email to remove a particular user from the list.


### Step 3. Add safes to the group


The "Safes" item of the group menu opens a dialog to control the safe list of the group. As a site admin, you can only add safes that you created or for which you have "owner" rights. For each safe, you can set group access rights: "Can Edit", "Can view", or "Limited view".


![Group Safes](/img/group_safes_dropdown.jpg)


Later on, you can change the access rights or remove a safe from the group list.

![Group Safes List](/img/group_safes_list.jpg)


You can view and control group membership of a particular user by clicking the user email on the left pane:


![User dialog](/img/iam_user_dialog.jpg)

## Connect PassHub to Active Directory (LDAP, Azure)

PassHub for Business can sync its users to a company Active Directory (AD).

The first time a user logs in to PassHub (at the time the user account is created), the user provides their AD credentials (the user principal name (UPN) and a password). The credentials are checked by AD, and the user account is bound to the AD records.

To identify a user for safe sharing or PassHub safe group membership, PassHub relies on a user mail provided by the AD. In the absence of the user email address, PassHub uses the UPN.


Every time a user logs in to PassHub, the user's membership in a specific AD group of "PassHub users" is checked. Another AD group, "PassHub admins," gives its members admin rights for PassHub.


When PassHub is connected to the Active Directory, user rights (active, admin, or disabled) are defined by AD group membership. To prevent conflicts, the corresponding elements in the PassHub "User Management Page" are only used to indicate user state, not to control it.

There is an almost one-to-one mapping of user rights in standalone PassHub and PassHub AD:

**Authorized** - the user is a member of the "PassHub users" group but has not created a PassHub account yet.

**Active** - a member of the "PassHub users" group with a PassHub account.

**Admin** - same as active, plus a member of "PassHub admin".

**Disabled** - The user has a PassHub account but their "PassHub user" group membership was revoked.

The parameters of the PassHub connection to the Active directory are defined by a structure in the PassHub config file; see the template below.


```php

define(
    'LDAP', [
      // Active directory server schema, name and port
      'url' => 'ldaps://ad.yourcompany.com:636',

      'base_dn' => "OU=AADDC Users,DC=yourcompany,DC=com",

      // When creating a new user account, 
      // Passhub identifies a user by the User Principal Name (upn), 
      // which consists of a user name (logon name), separator (the @ symbol), and 
      // a domain name (UPN suffix). In case the user provides only username, without
      // @-symbol and domain, the `domain` parameter is added to obtain the UPN

      'domain' => "yourcompany.com",

      // Group names, which allows to access PassHub and provides admin rights
      'group' => "CN=PassHub Users,OU=AADDC Users,DC=yourcompany,DC=com",
      'admin_group' => "CN=PassHub Admins,OU=AADDC Users,DC=yourcompany,DC=com",

      // credentials used by Passhub itself when cheking user membership to the above group
      'bind_dn' => "azureldap@yourcompany.com",
      'bind_pwd' => "12345678",
    ]
);

```


## Deploying PassHub to Azure

You can deploy PassHub for Business to Azure and connect it with Azure Active Directory via LDAP. 

1. Create an Azure subscription and Active Directory tenant. Azure Active Directory Domain Services managed domain should be enabled and configured. The following Microsoft tutorial guides through the details of Azure Active Directory Domain Services configuration: [https://learn.microsoft.com/en-us/azure/active-directory-domain-services/tutorial-create-instance](https://learn.microsoft.com/en-us/azure/active-directory-domain-services/tutorial-create-instance)

2. Configure LDAP for an Azure Active Directory Domain Services managed domain. Please follow this Microsoft tutorial to complete the LDAP setup: [https://learn.microsoft.com/en-us/azure/active-directory-domain-services/](https://learn.microsoft.com/en-us/azure/active-directory-domain-services/tutorial-configure-ldaps)

3. Once the LDAP server is up and running, follow the above paragraph [#connect-passhub-to-active-directory-ldap-azure](#connect-passhub-to-active-directory-ldap-azure) to deploy PassHub for Business and perform PassHub configuration.


