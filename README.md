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
  enable_new_listings: true,
  enable_edit_sort: true,
  enable_edit_display: true,
  enable_edit_core: true,
  core_display: true,
  enable_edit_nft: true,
  nft_display: true,
  enable_edit_pnft: true,
  pnft_display: true,
  enable_edit_cnft: true,
  cnft_display: true,
  fee_create: 0,
  fee_execute: 0,
  treasury: "",
  collections: "6Gfz6beNCcP8P7vrMyN2AFtsuv8rkVszSJ8xoP4zQyaR,ACy3ZVXcch8mZXUtRVqsJfa2DhFHxnUJpBb4oeN9tZsX,BL8ocmGmaEiM73JYjAAhgAmHPbtuY3CThYem9g4N5PqQ,BTJPWLW7DLQWpm2TNNEByAM5a1E1AGJp4h43czo9YBLc,Cq2BNRoE5RqyqSmACDQLx4ivp3MgmePwd2mdroZ5hmom,H3mnaqNFFNwqRfEiWFsRTgprCvG4tYFfmNezGEVnaMuQ",
  sellers: "7Z3LJB2rxV4LiRBwgwTcufAWxnFTVJpcoCMiCo8Z5Ere,2jcih7dUFmEQfMUXQQnL2Fkq9zMqj4jwpHqvRVe3gGLL",
  enable_edit_sellers: true,
  enable_edit_collections: true,
  master_settings: true,
  collections_display: true,
  sellers_display: true,
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

| **Parameter** |    **Type**     | **Required** |   **Default**   | **Description**          |
| :------------ |:---------------:|:------------:|:---------------:|:-------------------------|
| id            | string          |   yes        |  false          |                          |
| name          | string          |   no         |  McSwap Shop    |                          |
| logo          | url             |   yes        | ./img/logo.png  |                          |