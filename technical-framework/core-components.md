# Core Components

1. **BaseHook Integration:** Levery extends Uniswap V4's `BaseHook`, utilizing its functionalities to inject custom logic into key transaction points, such as before and after swaps and liquidity events. This allows for real-time interventions to adjust fees and ensure compliance with trading rules.
2. **Chainlink Oracles:** The platform uses Chainlink’s reliable and secure oracles to fetch real-time prices. These oracles are crucial for the dynamic adjustment of pool fees and for providing the latest market data to mitigate risks associated with price discrepancies.
3. **Dynamic Fee Adjustment:** Levery's contract includes mechanisms to adjust the swap fees dynamically:
   * **setDynamicFee:** Updates the dynamic swap fee for a pool based on the discrepancies between the latest oracle prices and pool prices.
   * **beforeSwap:** Adjusts the swap fee right before a transaction, ensuring that fees are optimized for current market conditions.
4. **Permission Management System:**
   * **PermissionManager:** Manages user permissions for swapping and liquidity management, critical for enforcing compliance protocols.
   * **Administrative Functions:** Includes functions like `updateBaseFee`, `setPoolBaseFee`, `setPoolOracle`, and `setPermissionManager`, allowing administrators to maintain control over the operational aspects of the platform.
5. **Price Calculation and Liquidity Hooks:**
   * **getCurrentPrices:** Utilizes `StateLibrary` and `TickMath` to calculate accurate prices within the pool.
   * **Liquidity Management Hooks:** `beforeAddLiquidity` and `beforeRemoveLiquidity` ensure that all liquidity operations are performed by authorized users, enhancing security and compliance.

**Implementation and Operational Details**

* **Deployment:** The initial setup involves deploying the contract with a designated pool manager and setting up the necessary Chainlink oracles and PermissionManager.
* **Usage Scenarios:** The platform catinally adjusts fees and permissions in real-time, ensuring efficient and secure operations tailored to the needs of financial institutions.
