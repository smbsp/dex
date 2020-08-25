# Decentralised Exchange - DEX - Blockchain - React and Solidity

Decentralised exchanges work as fully autonomous, decentralized applications (DApps), which allow traders to transact without giving control over their money to a trusted central authority, as is the case with their traditional centralized counterparts. The main benefits are increased privacy, security, and control over the funds. Drawbacks include low liquidity as well as reduced usability and speed.

## Description

There are many kinds of decentralized exchanges on Ethereum:<br>
•	The simpler ones only allow to trade ERC20 tokens<br>
•	While the most sophisticated ones allow you to trade more assets, with more advanced trading options like margin trading <br>

### 1.	Architecture of DEX

A DEX has the same architecture as any other decentralized application on Ethereum:<br>
•	User wallet<br>
•	Frontend (Web)<br>
•	Smart contract (Blockchain)<br>

The logic of the DEX is inside one smart contract. A frontend is connected to the smart contract, so that end-user have a nice and easy-to-use interface to the smart contract. The frontend connects to the user wallet. The user wallet will prompt the user for confirmation before sending any transaction to the smart contract. The user wallet can be any Ethereum wallet, like Metamask. <br>

### 2.	Trading Sequence

We have 2 traders, Bob and Alice:<br>
•	Bob wants to buy 1 ABC token, at a price of up to 2 Ethers<br>
•	Alice wants to sell 1 ABC token, for whatever price<br>

Flow:<br>

•	Bob sends 2 Ethers to the DEX smart contract.<br>
•	Bob creates a buy limit order (explained later) for a limit price of 2 Ethers, amount of 1 ABC token, and send it to DEX smart contract<br>
•	Alice sends 1 ABC token to the DEX smart contract<br>
•	Alice creates a sell market order (explained later) for an amount of 1 ABC token, and send it to DEX smart contract<br>
•	The smart contract matches Bob and Alice order, and carry out the trade. Bob now owns 1 ABC token and Alice 2 Ethers<br>
•	Bob withdraws his 1 ABC token from the DEX smart contract<br>
•	Alice withdraws her 2 Ethers from the DEX smart contract<br>
 
### 3.	Wallet

Before users can trade, they need to transfer their ERC20 tokens to the smart contract of the DEX. They will:<br>
•	click on a button in the frontend that it will initiate the transfer<br>
•	confirm the transaction with their wallet<br>
•	and the tokens will be sent at the address of the smart contract<br>

Users can also withdraw their tokens from the DEX smart contract, once they have finished to trade. The DEX smart contract has its own ledger to track the ownership of Tokens & Ether. The ledger will be incremented when assets are added, and decremented when assets are withdrawn.<br>
 
### 4.	Order Types

Traders express their intent to trade by creating an order. An order has several fields:<br>
•	Currency (the asset you want to trade)<br>
•	Amount: how much you want to trade<br>
•	There are 2 main types of orders:<br>
a)	Limit order, which specify a max/min limit price for buy/sell order.<br>
b)	Market order, where you agree to whatever price is on the market<br>

### 5.	Orderbook

The orderbook is the core part of the DEX. It:<br>
•	Lists all limit orders<br>
•	Matches incoming market orders against existing limit orders<br>
•	Remove limit orders that were executed<br>

Orderbooks follow a price-time algorithm. When an incoming market order arrive, the orderbook will try to match it with the market order that has the best price. If several limit orders have the same price, the one that was created first get matched in priority.<br>

### 6.	Settlement

After a market and a limit order have been matched, we need to complete the transaction by sending the assets to their new owners:<br>
•	Tokens need to be transferred from the seller to the buyer<br>
•	and Ether needs to be transferred from the buyer to the seller<br>

The trick is that these transfers only take place symbolically. As we discussed before, all the assets are held in the wallet of the DEX smart contract at the moment of the trade. So, we only have to update the internal ledger of the DEX smart contract to reflect the asset transfer.
After the trade, the 2 traders will have to use the withdraw function of the wallet of the DEX smart contract to get back their asset.<br>

## Installation

Clone the repository and run the following commands for starting the Front End

```bash
npm install
npm run start
```

## Things I learnt #BUIDLing this application

1. **Template literals (Template strings)**: Template literals are string literals allowing embedded expressions. You can use multi-line strings and string interpolation features with them.They were called "template strings" in prior editions of the ES2015 specification. You can read more about it [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals).

2. **SASS**: Sass (short for syntactically awesome style sheets) is a preprocessor scripting language that is interpreted or compiled into Cascading Style Sheets (CSS). SassScript is the scripting language itself. You can read more about it [here](https://sass-lang.com/).

3. **Recharts**:  Recharts is a Redefined chart library built with React and D3. You can read more about it [here](https://www.npmjs.com/package/recharts).

4. **react-moment**: React component for the moment date library. You can read more about it [here](https://www.npmjs.com/package/react-moment).