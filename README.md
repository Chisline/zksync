# zkSync: scaling and privacy engine for Ethereum

[![Logo](zkSyncLogo.svg)](https://zksync.io/)

[![Live on Mainnet](https://img.shields.io/badge/wallet-Live%20on%20Mainnet-blue)](https://wallet.zksync.io)
[![Live on Rinkeby](https://img.shields.io/badge/wallet-Live%20on%20Rinkeby-blue)](https://rinkeby.zksync.io)
[![Live on Ropsten](https://img.shields.io/badge/wallet-Live%20on%20Ropsten-blue)](https://ropsten.zksync.io)

zkSync is a scaling and privacy engine for Ethereum. Its current functionality scope includes low gas transfers of ETH
and ERC20 tokens in the Ethereum network.

## Description

zkSync is built on ZK Rollup architecture. ZK Rollup is an L2 scaling solution in which all funds are held by a smart
contract on the mainchain, while computation and storage are performed off-chain. For every Rollup block, a state
transition zero-knowledge proof (SNARK) is generated and verified by the mainchain contract. This SNARK includes the
proof of the validity of every single transaction in the Rollup block. Additionally, the public data update for every
block is published over the mainchain network in the cheap calldata.

This architecture provides the following guarantees:

- The Rollup validator(s) can never corrupt the state or steal funds (unlike Sidechains).
- Users can always retrieve the funds from the Rollup even if validator(s) stop cooperating because the data is
  available (unlike Plasma).
- Thanks to validity proofs, neither users nor a single other trusted party needs to be online to monitor Rollup blocks
  in order to prevent fraud.

In other words, ZK Rollup strictly inherits the security guarantees of the underlying L1.

To learn how to use zkSync, please refer to the [zkSync SDK documentation](https://zksync.io/api/sdk/).

## Development Documentation

The following guides for developers are available:

- Installing development dependencies: [docs/setup-dev.md](docs/setup-dev.md).
- Launching zkSync locally: [docs/launch.md](docs/launch.md).
- Development guide: [docs/development.md](docs/development.md).
- Repository architecture overview: [docs/architecture.md](docs/architecture.md).

## Projects

- [zkSync server](core/bin/server)
- [zkSync prover](core/bin/prover)
- [JavaScript SDK](sdk/zksync.js)
- [Rust SDK](sdk/zksync-rs)

## Changelog

Since the repository is big and is split into independent components, there is a different changelog for each of its
major parts:

- [Smart contracts](changelog/contracts.md)
- [Core](changelog/core.md)
- [Infrastructure](changelog/infrastructure.md)
- [JavaScript SDK](changelog/js-sdk.md)
- [Rust SDK](changelog/rust-sdk.md)

## License

zkSync is distributed under the terms of both the MIT license and the Apache License (Version 2.0).

See [LICENSE-APACHE](LICENSE-APACHE), [LICENSE-MIT](LICENSE-MIT) for details.

### Proposal: Implement Gas Fee Optimization Mechanisms

Objective:
The goal of this proposal is to explore and implement optimization mechanisms to reduce gas fees for transactions on zkSync, thereby improving the affordability and accessibility of the platform for users.

Background:
Gas fees on the Ethereum network can fluctuate significantly, impacting the cost-effectiveness of transactions on zkSync. By implementing gas fee optimization mechanisms, we can mitigate the impact of high gas prices and provide users with a more predictable and cost-efficient experience.

Ideas for Gas Fee Optimization:
- Gas Price Prediction: Develop algorithms to predict gas prices based on historical data, network congestion, and other relevant factors. By accurately forecasting gas prices, users can optimize transaction timings to minimize gas costs.
- Dynamic Gas Price Adjustment:Implement mechanisms to dynamically adjust gas prices based on real-time network conditions. By dynamically setting gas prices, users can benefit from lower fees during periods of low network activity.
- Batching Transactions:Explore the feasibility of batching multiple transactions into a single transaction to reduce gas costs per operation. Batching similar transactions, such as token transfers or withdrawals, can optimize gas usage and lower overall fees.
- Gas Fee Subsidization:Introduce mechanisms to subsidize gas fees for users during peak network congestion or for high-value transactions. By subsidizing gas fees, zkSync can incentivize usage and ensure affordability for users.

Implementation Plan:
- Research and Analysis: Conduct thorough research on existing gas fee optimization techniques and analyze their applicability to zkSync.
- Design Proposal: Develop a detailed proposal outlining the chosen gas fee optimization mechanisms, including implementation details and expected benefits.
- Prototype Development: Implement a prototype of the proposed gas fee optimization mechanisms, focusing on functionality and efficiency.
- Testing and Optimization: Conduct comprehensive testing to evaluate the performance, reliability, and cost-effectiveness of the implemented mechanisms. Optimize the implementation based on testing results and user feedback.
- Documentation and Deployment: Prepare documentation covering the implementation details, usage guidelines, and best practices for leveraging gas fee optimization mechanisms. Deploy the optimized gas fee mechanisms to the zkSync platform.

  Expected Impact:
- Lower gas fees for transactions on zkSync, improving affordability and accessibility for users.
- Increased user satisfaction and adoption due to improved cost-effectiveness of using zkSync for Ethereum transactions.
- Enhanced competitiveness of zkSync compared to other layer-2 scaling solutions, attracting more users and developers to the platform.

Conclusion:
Implementing gas fee optimization mechanisms is crucial for improving the usability and affordability of zkSync. By reducing gas fees, we can enhance the overall user experience and drive greater adoption of zkSync as a scalable and cost-effective solution for Ethereum transactions.
