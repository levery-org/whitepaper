# Price Feed Oracle Integration

Levery integrates Chainlink's Price Feed oracle to access accurate and dependable market price data, which is essential for maintaining equitable pricing and computing dynamic fees within its platform. Utilizing a sophisticated Decentralized Data Model along with Offchain Reporting (OCR), these price feeds aggregate data effectively. This approach allows Levery to guarantee the integrity and precision of its calculations, ensuring that all pricing and fee adjustments are grounded in reliable and current market information.

### **Levery’s Use of Price Oracles**

Levery leverages the price feeds for several critical functionalities:

**Dynamic Fee Calculation**

Dynamic fees are crucial for adjusting transaction costs in response to market volatility and trading volume. The real-time data enables Levery to adjust fees dynamically, which helps protect liquidity providers from potential losses due to rapid price changes and provides traders with fair transaction costs.

**Maintaining Fair Pricing**

Accurate price information is essential for fair trade execution on Levery's platform. By using decentralized and reliable price feeds, Levery ensures that the prices used for trades are current and reflective of global market conditions.

**Mitigating Arbitrage Risks**

By integrating timely and accurate price data, Levery can identify and mitigate potential arbitrage opportunities that could be exploited due to price discrepancies across different markets. This ensures that the platform remains secure and profitable for all users.

### **How the Price Oracles Works**

**Data Aggregation**

Prices are sourced from numerous independent data providers and are aggregated in decentralized network of oracle nodes. This aggregation mitigates risks associated with single points of failure and ensures data reliability and security.

**Decentralized Oracle Network**

The data feeds are updated by multiple independent oracles, which collectively contribute to the robustness of the price data. Each oracle publishes data during aggregation rounds, which are then validated and aggregated into a single reliable price by an on-chain smart contract.

**Offchain Reporting (OCR)**

This feature enhances the efficiency of data aggregation by allowing oracles to reach consensus off-chain before publishing a single transaction on-chain. OCR reduces costs and improves the scalability of data feeds.

**Consumer and Proxy Contracts**

Consumer contracts are smart contracts that utilize the aggregated data. They interact with proxy contracts that point to the latest version of the aggregator contract, ensuring that upgrades to the data feed do not disrupt service.

### **Ensuring Market Integrity through Advanced Data Integration**

The incorporation of decentralized price feeds into Levery's framework highlights a trading environment that is secure, fair and efficient. This decentralized method of data aggregation bolsters the reliability of price information, which is pivotal in upholding transparency and trust within Levery's operations. By aligning with these core values, the integration plays a critical role in supporting the integrity and efficiency of the trading system.



