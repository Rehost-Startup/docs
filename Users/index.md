# ChippIn Docs | Users - Overview

Each new user is assigned a wallet through Rapyd API. 
All users register in Chippin through the app that makes all API calls to **Auth API**. The **Wallet API** is used to add funds to or transfer funds between wallets. Wallet API uses under lying **Rapyd Node SDK** to make all API calls to Rapyd Servers.

## Models

### User Model
The *User Object* contians the follwoing:

| Attribute   |      Type      |  Description |
|----------|:-------------:|:------|
| id | string | MongoDB-generated unique id. |
| name | string | Display name. This name is visible to all people in the group. |
| first_name | string | Real First Name of the user|
| last_name |  string | Real Last Name of the user |
| email |  string | Email of the user |
| passoword |  string | This password must contain atleast 8 characters. All passwords are stored in encrypted form. |
| walletId | string | Rapyd ewalletId |

The model can be found in `src/server/models/User.js`.

Read [Users Usage](Users/usage.md) complete implementation details involving Rapyd API.
