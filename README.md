# Simple Local Copier (SLC)

## Introduction
SLC is an Expert Advisor that allows you to copy trades from a master account to a slave account. This code serves as a sample implementation that demonstrates the basic functionality of the copier.

## Global Variables
- `LotMultiplier`: This variable determines the trade size customization for the slave account. The default value is 1.0.

## Expert Advisor
The Expert Advisor contains two main functions: `OnInit()` and `OnTick()`.

### `OnInit()`
- This function is called when the Expert Advisor is initialized.
- It connects to both the master and slave accounts using the `AccountInfoInteger()` function.
- If the connection to either of the accounts fails, an error message is printed, and the initialization fails.

### `OnTick()`
- This function is called on each tick of the price.
- It retrieves the current trade size from the master account using `SymbolInfoDouble()` and `MarketInfo()` functions.
- Calculates the trade size for the slave account by multiplying the master lot size with the `LotMultiplier`.
- It then attempts to copy the trade from the master account to the slave account using the `OrderSend()` function.
- If the trade is copied successfully, a success message is printed. Otherwise, an error message with the error code is printed.

## Custom Functions
- `SetLotMultiplier(double multiplier)`: This function allows you to set the `LotMultiplier` variable. It prints the updated value of the `LotMultiplier`.

## Program Start
- The `OnStart()` function is called when the program starts.
- It sets the `LotMultiplier` to 2.0 using the `SetLotMultiplier()` function.
- It then enters a while loop that runs indefinitely until the program is stopped.
- Inside the loop, the `OnTick()` function is called to copy the trade from the master account to the slave account.
- A 1-second delay is added using the `Sleep()` function before copying the next trade.

---

ForexRobotEasy is not the official developer of this product. We only provide a sample code that demonstrates the functionality described in this product. For detailed reviews and trading results of this product, please visit the official developer's website at [https://forexroboteasy.com/forex-robot-review/simple-local-copier-review-streamline-your-forex-trading/](https://forexroboteasy.com/forex-robot-review/simple-local-copier-review-streamline-your-forex-trading/).

Please note that the code provided here is a simplified version and may not include all the features and optimizations present in the official product. To access the official developer and obtain the complete version of this product, please refer to MQL5.
