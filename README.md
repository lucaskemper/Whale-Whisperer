# 🐋 Whale Whisperer: On-Chain Alpha from Smart Money Flows

**Track, analyze, and extract trading signals from crypto whale wallets.**  
Whale Whisperer is a research pipeline that monitors smart money activity across Ethereum and other EVM chains to detect early token accumulations, recurring profitable trades, and build real-time portfolio signals based on wallet clustering.

## 📈 Why This Matters

In crypto, wallets *are* hedge funds. By reverse-engineering the behavior of top-performing wallets, we can surface directional signals and identify new opportunities before the crowd.

This project is designed to:
- Identify **alpha-generating wallets** based on realized PnL
- Track token **accumulation patterns** across known smart money entities
- Construct a **token selection signal** based on real-time wallet flows
- Evaluate signal performance using backtesting and forward metrics

---

## 🧱 Architecture

| Module | Description |
|--------|-------------|
| `data/addresses/` | Curated lists of smart money wallet addresses (CT influencers, funds, DeFi whales) |
| `src/fetch_transactions.py` | Pulls historical ERC20 transfers and native txs for target wallets |
| `src/parse_flows.py` | Extracts token buys/sells from transaction logs |
| `src/label_alpha_trades.py` | Detects high-return trades and scores wallet performance |
| `src/generate_signals.py` | Aggregates wallet flows into token-level signals |
| `src/backtest_signal.py` | Evaluates performance vs. ETH/market cap-weighted benchmark |
| `dashboard/` | Interactive Streamlit app with whale dashboards and signal explorer |

---

## 🔍 Signal Logic

### Smart Money Token Accumulation Signal
1. Identify wallets with strong historical hit rate or total PnL
2. For each wallet, track recent ERC20 buys (via DEX or transfer patterns)
3. Aggregate token inflows across all high-scoring wallets
4. Create a weighted signal (token score = net inflows × wallet alpha rating)

---

## 📊 Sample Outputs

- 📈 Token signal scores ranked by wallet-adjusted inflows
- 🧠 Whale leaderboard with realized ROI and hit rate
- 🧪 Backtest of smart-money basket vs. ETH benchmark
- 💬 Optional Telegram or Twitter bot for live signal alerts

---

## 📦 Dependencies

- `web3.py`, `pandas`, `requests`, `tqdm`
- Optional: `plotly`, `streamlit`, `backtrader` for UI/backtest
- RPC Providers: [Alchemy](https://www.alchemy.com/), [Infura](https://infura.io/), [Moralis](https://moralis.io/)

---

## 🔐 Wallet Sources

Whale labels sourced from:
- [Arkham Intelligence](https://platform.arkhamintelligence.com/)
- [Debank Discover](https://debank.com/discover)
- GitHub open datasets (`smart_money_wallets.json`)
- Community-curated CT influencer lists

---

## 🧠 Future Work

- Add wallet clustering (KMeans or DBSCAN) to identify hidden groups
- Integrate L2s (e.g., Arbitrum, Optimism) using cross-chain APIs
- Create sector-based filters (e.g., DeFi, AI, RWAs)
- Detect *rotation behavior* across wallets (narrative alpha)

---

## 📜 License

MIT – Open source, research use only.  
If you fork or build on this for trading – DM me or cite the repo 😎

---

## 👨‍💻 Author

Lucas Kemper  
[linkedin.com/in/lucaskemper](https://linkedin.com/in/lucaskemper) · [github.com/lucaskemper](https://github.com/lucaskemper)  
MSc Finance · Crypto Quant Research · Market Regime Detection

