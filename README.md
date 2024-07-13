# Customized Uniswap V2 AMM Model and Fee

## Overview

This project forks the Uniswap V2 repository and customizes it to develop a new Automated Market Maker (AMM) model with the following modifications:

1. **Trading Fee Structure:** The trading fee has been adjusted from the default 0.3% to 0.5%.
2. **Liquidity Incentives:** A reward system for liquidity providers has been implemented.

## Uniswap V2 Core Components

### Factory Contract
The factory contract is responsible for managing the creation of pair contracts for each token pair. It keeps track of all pairs and allows users to create new ones.

### Pair Contract
The pair contract represents a liquidity pool for a specific token pair. It handles the core functionalities of the AMM, including minting, burning, and swapping tokens.

### ERC20 Implementation
Uniswap V2 uses ERC20 tokens to represent liquidity provider shares. These tokens follow the ERC20 standard and provide functions for transferring, approving, and managing balances.

## Customizations

### Trading Fee Adjustment

The trading fee has been modified from 0.3% to 0.5% by adjusting the fee parameters in the pair contract.

### Liquidity Incentives

A reward system for liquidity providers has been implemented. Liquidity providers earn rewards based on their contribution to the liquidity pool. The rewards are distributed proportionally and can be claimed by the providers.


#### 1. Factory Contract

The Factory contract is responsible for deploying new Pair contracts and keeping track of all pairs created by the protocol.

- **createPair(address tokenA, address tokenB):** Creates a new Pair contract for the specified token pair and returns its address.
- **getPair(address tokenA, address tokenB):** Returns the address of the Pair contract for the specified token pair.
- **allPairs(uint):** Returns the address of the Pair contract at the specified index.
- **allPairsLength():** Returns the total number of Pair contracts created.

#### 2. Router Contract

The Router contract is used to interact with the Uniswap V2 protocol, providing functions for adding/removing liquidity and performing token swaps.

- **addLiquidity:** Adds liquidity to a pair.
- **removeLiquidity:** Removes liquidity from a pair.
- **swapExactTokensForTokens:** Swaps an exact amount of input tokens for as many output tokens as possible.
- **swapTokensForExactTokens:** Swaps as few input tokens as possible for an exact amount of output tokens.

#### 3. Pair Contract

The Pair contract represents a liquidity pool for a specific token pair. It manages the liquidity provision, token swaps, and price calculations.

- **mint:** Mints liquidity tokens.
- **burn:** Burns liquidity tokens and returns the underlying assets.
- **swap:** Swaps one token for another.
- **sync:** Synchronizes the reserves of the pair.
## Links

- [Deployed Contracts on Sepolia Testnet](https://sepolia.etherscan.io/address/0xbc5b08ea28ca7121200051046c49a1031038d5cf, https://sepolia.etherscan.io/address/0xfbbfa982e174616e9ec27769b3b9a118d23ba4fa)

As of now, no pairs have been added to this implementation of the Uniswap V2 contracts on Sepolia testnet. Consequently, only new pairs must be created for testing . To use the functions usable, such as the addLiquidity function, fee adjustments, and the Automated Market Maker (AMM) liquidity rewards, these new pairs must be properly bootstrapped with initial liquidity. 
