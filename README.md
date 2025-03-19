# mcswap-shop
This module will embed a Solana NFT storefront into an existing application. Listings are powered by the native Solana programs of the McSwap Trustless Escrow Protocol. This module makes use of the [mcswap-sdk](https://github.com/SolDapper/mcswap-sdk) to directly integrate with the protocol.

![mcswap shop](https://repository-images.githubusercontent.com/944741416/d30f1c19-99a5-479f-ab66-ba9ab5d4c6e5)

![powered by solana](http://mcswap.xyz/gh/stacked-color.svg)

## install
```javascript
npm i mcswap-shop
```

## html
```html
<div id="my-market"></div>
```

## usage
```javascript
import shop from "mcswap-shop";
import "mcswap-shop/src/colors/green-shop.css";
const myshop = new shop(process.env.RPC);
myshop.init({
  id: "my-market",
  name: "McSwap Shop",
  logo: "",
  logo_link: "",
  default_priority: "Low",
  default_sort: "Newest First",
  default_display: "All Listings",
  text_intro: "Initializing Demo",
  text_buy: "Buy Me",
  master_settings: true,
  enable_new_listings: true,
  enable_edit_sort: true,
  enable_edit_display: true,
  fee_create: 0,
  fee_execute: 0,
  treasury: "",
  enable_edit_core: true,
  enable_edit_nft: true,
  enable_edit_pnft: true,
  enable_edit_cnft: true,
  core_display: true,
  nft_display: true,
  pnft_display: true,
  cnft_display: true,
  collections_display: true,
  enable_edit_collections: true,
  collections: "6Gfz6beNCcP8P7vrMyN2AFtsuv8rkVszSJ8xoP4zQyaR,ACy3ZVXcch8mZXUtRVqsJfa2DhFHxnUJpBb4oeN9tZsX,BL8ocmGmaEiM73JYjAAhgAmHPbtuY3CThYem9g4N5PqQ,BTJPWLW7DLQWpm2TNNEByAM5a1E1AGJp4h43czo9YBLc,Cq2BNRoE5RqyqSmACDQLx4ivp3MgmePwd2mdroZ5hmom,H3mnaqNFFNwqRfEiWFsRTgprCvG4tYFfmNezGEVnaMuQ",
  sellers_display: true,
  enable_edit_sellers: true,
  sellers: "7Z3LJB2rxV4LiRBwgwTcufAWxnFTVJpcoCMiCo8Z5Ere,2jcih7dUFmEQfMUXQQnL2Fkq9zMqj4jwpHqvRVe3gGLL",
  shop_styler: {
    shop:{
      "background": "#1a1a1a",
      "background-repeat": "no-repeat",
      "background-size": "cover",
      "background-position": "center"
    },
    wrapper:{
      // "background": "#000000eb"
    },
    header:{
      "color": "#fff"
    },
    titles:{
      "color": "#fff"
    },
    details:{
      "color": "#1367d4",
    },
    labels:{
      "color": "#1367d4",
    }
  }
});
```

## notes
if you're using a wallet connector other than [mcswap-connector](https://github.com/SolDapper/mcswap-connector), be sure to set window.mcswap = provider / window.mcswap = false when a wallet connects / disconnects. This allows your shop to update it's display including a "Delist" button on assets listed by the connected wallet.

## config options

| **Parameter**         |    **Type**     |      **Default**      | **Description**                           |
| :-----------------------|----------------:|:----------------------|:------------------------------------------|
| id                      | string          |  false (bool)         |                                           |
| name                    | string          |  McSwap Shop          |                                           |
| logo                    | url             |  false (bool)         |                                           |
| logo_link               | url             |  #                    |                                           |
| priority                | string          |  Low                  |                                           |
| default_sort            | string          |  Newest First         |                                           |
| default_display         | string          |  All Listings         |                                           |
| text_intro              | string          |  Initializing Market  |                                           |
| text_buy                | string          |  Buy Me               |                                           |
| master_settings         | bool            |  true                 |                                           |
| enable_new_listings     | bool            |  true                 |                                           |
| enable_edit_sort        | bool            |  true                 |                                           |
| enable_edit_display     | bool            |  true                 |                                           |
| fee_create              | float           |  0                    |                                           |
| fee_execute             | float           |  0                    |                                           |
| treasury                | string          |  false                |                                           |
| enable_edit_core        | bool            |  true                 |                                           |
| enable_edit_nft         | bool            |  true                 |                                           |
| enable_edit_pnft        | bool            |  true                 |                                           |
| enable_edit_cnft        | bool            |  true                 |                                           |
| core_display            | bool            |  true                 |                                           |
| nft_display             | bool            |  true                 |                                           |
| pnft_display            | bool            |  true                 |                                           |
| cnft_display            | bool            |  true                 |                                           |
| collections_display     | bool            |  true                 |                                           |
| enable_edit_collections | bool            |  true                 |                                           |
| collections             | csv             |  ""                   |                                           |
| sellers_display         | bool            |  true                 |                                           |
| enable_edit_sellers     | bool            |  true                 |                                           |
| sellers                 | csv             |  ""                   |                                           |
| shop_styler             | obj             |  false (bool)         |                                           |

### shop_styler object
the styler object lets you add some css to fine tune your shop's color scheme
```javascript
  {
    shop:{
      "background": "#1a1a1a",
      "background-repeat": "no-repeat",
      "background-size": "cover",
      "background-position": "center", // add css style to your shop background
    },
    wrapper:{
      // "background": "#000000eb" // optional layer between background and shop content
    },
    header:{
      "color": "#fff", // page name color
    },
    titles:{
      "color": "#fff", // listing title color
    },
    details:{
      "color": "#1367d4", // listing price color 
    },
    labels:{
      "color": "#1367d4", // settings page label color
    }
  }
```