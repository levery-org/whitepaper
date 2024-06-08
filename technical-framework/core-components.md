# Core Components

### Overview

Levery's hook smart contract, built atop the Uniswap V4 framework, incorporates a variety of sophisticated features designed to facilitate dynamic fee management, enforce compliance through permissions, and integrate with real-time price oracles. Core components that harness the power of decentralized finance technology to enhance functionality, compliance, and efficiency, critical for institutional adoption and regulatory approval.

### Uniswap V4 BaseHook Integration

The Levery contract extends `BaseHook` from Uniswap V4's periphery, which is a foundational component allowing the integration of custom logic at specific points in the liquidity pool lifecycle. This enables Levery to implement custom behaviors for trading actions, such as swaps and liquidity management.

The hooks (`beforeSwap`, `beforeAddLiquidity`, `beforeRemoveLiquidity`) are crucial for pre-transaction checks and adjustments. They allow Levery to:

* Enforce permissions dynamically.
* Adjust fees based on current market data and predefined rules.
* Ensure transactions are only executed when all compliance and risk management criteria are met.

### Permission Manager

A vital component of Levery's contract is the `PermissionManager`. This module controls access to liquidity provision and swap actions, ensuring that only authorized users can perform these operations. It plays a critical role in maintaining compliance with regulatory standards, thereby ensuring that all trading activities align with legal requirements.

### Dynamic Fee Structure

At the heart of Levery's trading mechanism is the dynamic fee structure, governed by variables such as `baseFee` and `lpFeeMultiplier`. These parameters are adjustable by the admin and are used to calculate trading fees based on current market conditions and pool-specific settings.

* `baseFee`: Represents the default fee percentage for swaps within the pools, set by the admin.
* `lpFeeMultiplier`: Used to adjust the liquidity provider's fee share, allowing fees to be responsive to market dynamics and volatility.

### Pool-Specific Oracle Integration

Each liquidity pool can be assigned its specific price feed oracle through a mapping `poolOracles`), which stores oracle addresses and comparison flags to ensure price accuracy for fee calculations. This setup enables the contract to fetch real-time data to make informed decisions on fee adjustments.

### **Pool Settings**

Levery's architecture includes the ability to tailor settings for individual pools via mappings that link pool identifiers to specific configurations:

* `poolBaseFees`: Maps pool identifiers to customized base fees for each pool, allowing for tailored fee structures that can adapt to the unique characteristics of each token pair.
* `poolOracles`: Links each pool to a designated oracle, facilitating accurate price feeds that are crucial for setting appropriate swap fees and mitigating arbitrage risks.

### Enhanced Price Calculation

Each pool can be associated with a price feed oracle, specified in the `PoolOracle` struct, which includes the oracle address and a flag indicating whether to compare against `price0` or `price1`.&#x20;

Utilizing Chainlink's `AggregatorV3Interface` and internal libraries like `TickMath` and `FullMath`, the contract calculates precise token prices within a pool. This integration allows Levery to fetch real-time price data and is crucial for maintaining balance in response to market movements.

* `getLastOraclePrice`: Fetches the latest price from a specified price feed oracle, adjusting for token decimals to ensure consistency across different assets.
* `getCurrentPrices`: Calculates current prices within a pool, using advanced mathematical libraries like `TickMath` and `FullMath` to ensure precision.

### Admin Controls

The contract is equipped with administrative functions that allow for high-level control and configuration:

* `setAdmin` and `updateAdmin`: Functions to set and update the administrator's address.
* `updateBaseFee` and `setPoolBaseFee`: These functions allow the admin to adjust fee parameters globally or per pool, responding to evolving market dynamics.
* `setPermissionManager`: Assigns a new `PermissionManager`, updating the contract's access control logic.



