# Uniswap V4

## **Overview**

Uniswap, a prominent decentralized exchange (DEX), has significantly shaped the DeFi landscape by providing an automated mechanism for token exchanges. It uses liquidity pools instead of traditional market orders, allowing for decentralized, permissionless trading.

Uniswap is a decentralized exchange (DEX) that has significantly shaped the decentralized finance (DeFi) landscape by allowing automated swapping of ERC-20 tokens via a series of smart contract-driven liquidity pools. It eliminates the need for traditional market-making processes, facilitating seamless, trustless token swaps directly on the Ethereum blockchain.

1. **Uniswap V1 (2018):** The first version introduced the automated market maker (AMM) model using a constant product formula (xy = k). It allowed for direct swaps between Ethereum (ETH) and any ERC-20 token, setting the foundational structure for decentralized exchanges.
2. **Uniswap V2 (2020):** Building on the initial design, V2 introduced ERC-20 to ERC-20 swaps, enhanced price oracle functionality, and added features like flash swaps, broadening the scope and flexibility of the platform.
3. **Uniswap V3 (2021):** V3 further innovated by introducing concentrated liquidity and multiple fee tiers. This allowed liquidity providers to allocate their funds within custom price ranges, enhancing capital efficiency and market depth.
4. **Uniswap V4 (Expected Deployment in Q2 of 2024):** The forthcoming V4 introduces a revolutionary Singleton design, reducing gas costs and improving transaction efficiency. It consolidates all liquidity pools into a single contract and introduces advanced features like hooks, flash accounting, and direct native ETH support.

***

## Technical Architecture of Uniswap V4

Uniswap V4 introduces significant architectural advancements with its Singleton contract structure, replacing the multiple contracts per pair in earlier versions. This consolidation significantly reduces gas costs and simplifies the creation and management of liquidity pools by enabling all transactions to occur within a single contract. This not only reduces the operational overhead but also decreases the gas costs for trading and pool creation by up to 99%.

Another novel feature in V4 is the flash accounting system, which allows users to chain multiple actions, like swaps and liquidity additions, in a single transaction. This system ensures all token balances are settled by the end of the transaction, reverting if the debts are not properly cleared, thus enhancing transaction security and efficiency.

V4 also introduces hooks, which are customizable smart contracts that can be attached to liquidity pools to allow specific functionalities to be executed at various stages of the pool's lifecycle.&#x20;

Additionally, V4 supports direct trading pairs with native Ethereum (ETH), eliminating the need for wrapped ETH and streamlining the trading process. This adjustment not only simplifies the trading steps but also potentially lowers transaction fees.

### What is a Hook in Uniswap V4?

Hooks in Uniswap V4 are programmable smart contracts that can be attached to liquidity pools to modify their behavior at crucial operational stages, such as before and after swaps, or during liquidity changes. These hooks provide developers with the ability to implement customized functionalities, ranging from transaction validation processes to complex fee-adjustment algorithms, directly within the liquidity pool's lifecycle.

{% hint style="info" %}
**Uniswap Docs:** [https://docs.uniswap.org](https://docs.uniswap.org/)

**Introduction to Uniswap V4:** [https://docs.uniswap.org/contracts/v4/concepts/intro-to-v4](https://docs.uniswap.org/contracts/v4/concepts/intro-to-v4)
{% endhint %}
