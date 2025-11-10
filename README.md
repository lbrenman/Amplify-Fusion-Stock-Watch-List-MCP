# Amplify Fusion Stock Watch List MCP

An MCP Server demonstration implemented in Amplify Fusion for checking a stock watch list

* Leverages the services in the [Amplify Fusion Stock Watch List API](https://github.com/lbrenman/ai-stockquote-fh)
* Requires a [Finnhub](https://finnhub.io/) API Key and a Postgres Server
* MCP Server API Key is used as userid for Database

Current tools:

* AddSymbolToStockWatchList - Add a stock symbol to my watch list
* GetStockQuote - Get stock quote based on symbol
* GetStockWatchList - Get my stock watch list
* GetStockWatchListSymbols - Get stock watch list symbols
* RemoveSymbolFromStockWatchList - Remove symbol from stock watch list

## Postgres Details

CREATE TABLE watchlist (
  id              SERIAL PRIMARY KEY,
  symbol          VARCHAR(100) NOT NULL,
  userid          VARCHAR(100) NOT NULL,
  created_at      TIMESTAMPTZ NOT NULL DEFAULT NOW()
);