# AI-Powered Grid Trading Bot

A Python-based automated trading application with a Tkinter GUI. This bot implements a structured **Layered Entry (Grid) Strategy** using the Alpaca Trade API, allowing users to manage multiple equity positions with automated drawdown-based entries.

## 🚀 Overview
The bot is designed to automate a "Buy the Dip" strategy. Once an initial position is taken, it automatically calculates and places multiple limit orders at specific drawdown levels (e.g., every 5% drop) to lower the average entry price.

## ✨ Key Features
* **Automated Grid Management:** Automatically calculates entry levels based on user-defined drawdown percentages.
* **Real-time Alpaca Integration:** Uses Alpaca's REST API for order execution and position tracking.
* **Persistent Data:** Saves your portfolio and strategy state in a local `equities.json` file.
* **Interactive GUI:** * Add/Remove stocks easily.
    * Toggle trading systems on/off for specific symbols.
    * Integrated AI Chat simulation for strategy assistance.
* **Multi-threaded Execution:** Background threads handle order monitoring without freezing the interface.

## 🛠️ Tech Stack
* **Language:** Python 3.x
* **GUI:** Tkinter
* **Broker API:** Alpaca Trade API (`alpaca-trade-api`)
* **Data Format:** JSON

## 🔧 Installation & Setup
1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/diogoamar0/AI-Trading-Bot.git](https://github.com/diogoamar0/AI-Trading-Bot.git)
    cd AI-Trading-Bot
    ```
2.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```
3.  **API Configuration:**
    Open `main.py` and replace the `key` and `secret_key` variables with your Alpaca credentials. **Note:** Use Paper Trading keys for testing.

4.  **Launch the App:**
    ```bash
    python main.py
    ```

## 📈 Trading Logic
1.  **Initial Order:** When a system is toggled "On", the bot places a market order for 1 share.
2.  **Drawdown Levels:** Based on the `Levels` and `Drawdown%` inputs, the bot generates limit buy orders below the market price.
3.  **Persistence:** The bot tracks filled levels in `equities.json` to avoid duplicate orders.

## ⚠️ Risk Warning
This bot places multiple real orders. Ensure you have sufficient buying power and understand the risks of layered entry strategies. The "AI Chat" feature is currently a mock simulation for educational purposes.
