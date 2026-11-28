# FlashBTC PRO

A desktop bitcoin flasher terminal for generating fake Bitcoin transaction receipts and simulating Trust Wallet deposits. Built with a C++ backend for USB hardware interaction and a Python (CustomTkinter) frontend for a sleek, dark-themed graphical interface.

## ⚠️ WARNING: READ THIS FIRST

**This is a spoofed BTC tool for researcher. It does not generate, mine, or transfer real Bitcoin.** 

* **Do NOT use this to scam people.** Using this tool to deceive individuals into believing they have received a real Bitcoin transaction is illegal, unethical, and constitutes fraud. You will get caught, and you will face legal consequences. This repository is for educational purposes, UI/UX demonstration, and social engineering awareness training only.
* **No Real Blockchain Interaction:** The "Send to Trust Wallet" button only triggers a local UI popup. It does not connect to the Bitcoin network, it does not broadcast transactions, and it cannot alter the balance of a real Trust Wallet app.
* **No Spendable Crypto:** The `.json` files written to the USB drive are just text files. They hold zero monetary value and cannot be imported into any real wallet.

## Why does this exist?

Most "flash Bitcoin" tools floating around on Telegram and Discord are scams designed to steal *your* money. They either contain malware or ask you to pay a "network fee" to generate fake coins. 

I built FlashBTC PRO as a reverse-engineering project and a UI demonstration. It shows exactly how these fake tools operate under the hood: they generate a fake payload, write it to a piece of hardware, and use a custom UI to make it look legitimate. It’s a great way to understand the mechanics of social engineering scams without actually breaking the law or getting infected with malware.

## Features

* **Password Protected:** Gated entry (`Get at password.txt inside the folder`)
* **Auto-Detect Hardware:** Scans Windows logical drives for removable USB storage devices.
* **Payload Generation:** Generates a mock `FlashBTC_Receipt.json` file containing a fake TXID, timestamp, and target address, writing it to both the local disk and any detected USB drives.
* **Wallet Popup:** A graphical modal that mimics a Trust Wallet deposit screen.
* **Stealth UI:** Pure black background with tactical blue buttons.

## Project Structure

```text
FlashBTC-PRO/
│
├── src/
│   ├── backend/
│   │   └── main.cpp           # C++ Windows API backend (no external libraries)
│   │
│   └── frontend/
│       ├── app.py             # Python CustomTkinter GUI
│       └── requirements.txt   # Python dependencies
│
├── bin/
│   └── flashbtc.exe           # Auto-generated C++ backend
│
├── build_backend.bat          # Compiles C++ backend
└── run_app.bat                # Sets up Python venv and launches GUI
