# Swarm Trading SDK Examples

This repository contains comprehensive examples demonstrating how to use the Swarm Trading SDK Collection for trading Real World Assets (RWAs) across multiple platforms.

## 🚀 Quick Start

### Prerequisites

- Python 3.8 or higher
- A Swarm account with API credentials
- A wallet with some tokens for testing

### 1. Clone the Repository

```bash
git clone https://github.com/SwarmMarkets/python-swarm-sdks-examples.git
cd python-swarm-sdks-examples
```

### 2. Create a Virtual Environment

```bash
# Create virtual environment
python3 -m venv venv

# Activate virtual environment
# On macOS/Linux:
source venv/bin/activate

# On Windows:
venv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure Environment Variables

Create a `.env` file in the examples directory with your credentials:

```bash
# Required for all examples
PRIVATE_KEY=your_wallet_private_key_here

# Required for Market Maker and Trading SDK examples
RPQ_API_KEY=your_rpq_api_key_here

# Required for Cross-Chain Access and Trading SDK examples
USER_EMAIL=your_email@example.com

# Optional: Set environment (dev/prod)
SWARM_COLLECTION_MODE=dev  # or 'prod' for production
```

⚠️ **Security Warning**: Never commit your `.env` file to version control!

### 5. Run Examples

```bash
# Cross-Chain Access SDK - Stock market RWA trading
python example_cross_chain_access.py

# Market Maker SDK - Decentralized OTC trading
python example_market_maker.py

# Trading SDK - Unified multi-platform trading with smart routing
python example_trading.py

# Error Handling - Comprehensive error handling patterns
python example_error_handling.py

# RPQ Service - Low-level RPQ API client
python example_rpq_updated.py
```

## 📚 Available Examples

### 1. Cross-Chain Access SDK (`example_cross_chain_access.py`)

Demonstrates trading Real World Assets through the stock market API.

**Features:**

- Check market hours and trading availability
- Get real-time quotes for RWA tokens
- Check account status and available funds
- Execute buy/sell trades with USDC
- Cross-chain trading with `target_chain_id` parameter

**Use Case:** Best for trading during stock market hours (14:30-21:00 UTC) with access to traditional market prices.

### 2. Market Maker SDK (`example_market_maker.py`)

Shows peer-to-peer RWA trading through smart contracts and the RPQ API.

**Features:**

- Browse available offers from other traders
- Get best offers for token pairs
- Get quotes for trades
- Execute trades against existing offers
- Create your own offers
- Cancel offers

**Use Case:** 24/7 decentralized trading with on-chain settlement.

### 3. Trading SDK (`example_trading.py`)

Unified SDK that automatically chooses the best platform for your trades.

**Features:**

- Get quotes from all platforms simultaneously
- Compare prices across platforms
- Execute trades with smart routing strategies
- Automatic fallback handling
- Multiple routing strategies (BEST_PRICE, MARKET_MAKER_FIRST, etc.)

**Use Case:** Recommended for most users - automatically finds the best price and handles platform availability.

**Available Routing Strategies:**

- `BEST_PRICE` - Compares prices and selects the cheapest option (default)
- `CROSS_CHAIN_ACCESS_FIRST` - Tries Cross-Chain Access first, falls back to Market Maker
- `MARKET_MAKER_FIRST` - Tries Market Maker first, falls back to Cross-Chain Access
- `CROSS_CHAIN_ACCESS_ONLY` - Only uses Cross-Chain Access (no fallback)
- `MARKET_MAKER_ONLY` - Only uses Market Maker (no fallback)

### 4. Error Handling (`example_error_handling.py`)

Comprehensive guide to handling errors across all SDKs.

**Features:**

- Cross-Chain Access specific errors (market closed, account blocked, etc.)
- Market Maker specific errors (no offers, insufficient balance, etc.)
- Trading SDK fallback scenarios
- Web3/blockchain errors
- Best practices for error handling

## 📖 SDK Documentation

For detailed documentation on each SDK, refer to the main repository:

- **Cross-Chain Access SDK**: [Documentation](https://github.com/SwarmMarkets/python-swarm-sdks/blob/main/docs/cross_chain_access_sdk_doc.md) | [API Reference](https://github.com/SwarmMarkets/python-swarm-sdks/blob/main/docs/cross_chain_access_sdk_references.md)
- **Market Maker SDK**: [Documentation](https://github.com/SwarmMarkets/python-swarm-sdks/blob/main/docs/market_maker_sdk_doc.md) | [API Reference](https://github.com/SwarmMarkets/python-swarm-sdks/blob/main/docs/market_maker_sdk_references.md)
- **Trading SDK**: [Documentation](https://github.com/SwarmMarkets/python-swarm-sdks/blob/main/docs/trading_sdk_doc.md) | [API Reference](https://github.com/SwarmMarkets/python-swarm-sdks/blob/main/docs/trading_sdk_references.md)

## 🌐 Supported Networks

- Ethereum Mainnet
- Polygon
- Arbitrum
- Optimism
- Base

## 💡 Tips

1. **Start with the Trading SDK** - It provides the best user experience with automatic platform selection and fallback handling.

2. **Test in Development Mode** - Set `SWARM_COLLECTION_MODE=dev` in your `.env` file to use the development environment.

3. **Check Market Hours** - Cross-Chain Access is only available during stock market hours (14:30-21:00 UTC, Monday-Friday).

4. **Use Small Amounts** - Start with small trade amounts while learning the SDKs.

5. **Read Error Messages** - The SDKs provide detailed error messages to help you understand what went wrong.

## 🔐 Security Best Practices

1. **Never hardcode credentials** - Always use environment variables
2. **Keep your private key secure** - Never share it or commit it to version control
3. **Use a test wallet** - For development and testing
4. **Double-check addresses** - Verify token addresses before trading
5. **Start small** - Test with small amounts before larger trades

## 🆘 Support

- **GitHub Issues**: [Report bugs or request features](https://github.com/SwarmMarkets/python-swarm-sdks/issues)
- **Documentation**: [Full SDK documentation](https://github.com/SwarmMarkets/python-swarm-sdks)
- **Email**: developers@swarm.com

## 📄 License

MIT License - see the main repository for details.

## 🔗 Links

- **Main SDK Repository**: https://github.com/SwarmMarkets/python-swarm-sdks
- **Swarm Website**: https://swarm.com
- **PyPI Package**: https://pypi.org/project/swarm-collection/
