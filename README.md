# Adena SDK TS

Simple SDK to interact with the [Adena wallet](https://www.adena.app/) from your dApp 🚀

## ⚙️ Getting started

Install the packages:

```sh
npm install adena-sdk-ts
```

> ⚠️ The SDK isn't deployed on NPM yet, this command won't work. See
> the [Install in development](#install-in-development) section.

and use the exposed methods:

```ts
import { establishConnection, getAccountInfo, switchNetwork } from "adena-sdk-ts";

// Attempt to establish a connection
await establishConnection("my-app");

// Make sure the network is valid
await switchNetwork(constants.chainID);

// Get the account info
const accountInfo = await getAccountInfo();

console.log(accountInfo)
// {
//     "address": "g1rqgeem430ex2cns42azg3vajvuva92c4gthd7l",
//     "coins": "9999999000000ugnot",
//     "chainId": "dev",
//     "status": "ACTIVE",
//     "publicKey": {
//         "@type": "/tm.PubKeySecp256k1",
//         "value": "Aj6P/iW8JB4gYe86KrzR9Uzejv9iNpcNndMBMg4lLuFp"
//     },
//     "accountNumber": "0",
//     "sequence": "1"
// }
```

## 🔥 Features

This SDK supports almost all the methods currently available in Adena:

- General
    - `AddEstablish`
    - `GetAccount`
- Network
    - `SwitchNetwork`
    - `AddNetwork`
- Transactions
    - `DoContract`
    - `SignTx`
- Events
    - `On` (account and network changes)

They all include params and return type typing and JSDoc to enhance developer experience.

## 📈 Future improvements

This SDK is still under development and a lot of things can be improved:

- Support all the methods (missing `Sign` right now)
- Better typing
    - Transactions params typing isn't exactly correct for some cases
    - Not all the types of response are detailed in the documentation, some were found while testing but others may be
      missing.
- Integration with the official Adena repository
    - Instead of duplicating and rewriting the types here, the best way to ensure consistency would be to use a common
      packages of types in Adena wallet and this SDK.

## 💻 Install in development

Start by installing the dependencies, building and creating the package

```sh
yarn
yarn build
npm pack
```

then you can install it in your app

```sh
yarn add path-to-adena-sdk-ts.tgz
```

<div align="center">
  <h2>Made with ❤️ by</h2>
  <a href="https://github.com/RezaRahemtola">
    <img src="https://github.com/RezaRahemtola.png?size=85" width=85/>
    <br>
    <sub>Reza Rahemtola</sub>
  </a>
</div>
