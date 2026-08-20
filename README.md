# Python RSI 2 Level Strategy

<!-- START_HEADER -->

<!-- END_HEADER -->

This project demonstrates how to add an RSI-based trading strategy to a Python trading framework connected to MetaTrader 5.

The framework is first modified to make it more general-purpose and easier to extend with different strategies. The configuration file is moved into a configuration folder, and the configuration filename can be supplied on the command line. Command-line arguments can override values in the configuration file, including the MetaTrader path, testing mode, and trading cycle.

The main trading program is renamed to trading_bot and loads the selected strategy dynamically from the strategy folder. This makes it possible to change between the moving-average cross strategy, the RSI strategy, or another strategy by changing the configuration.

The RSI strategy uses two levels:

- When the RSI moves above the high trigger, the high trigger is set.
- If the RSI then falls below the high entry level, a sell trade is opened.
- When the RSI moves below the low trigger, the low trigger is set.
- If the RSI then rises above the low entry level, a buy trade is opened.
- Stop-loss and take-profit distances are supplied through the configuration.
- The strategy resets its trigger state after placing a trade.

The tutorial also adds general utility functions for obtaining bid and ask prices, calculating entry prices, and calculating stop-loss and take-profit levels for buy and sell trades. In testing mode, the close price is used because live bid and ask prices are not available.

The RSI indicator calculation is moved into a reusable indicators module. The strategy uses pandas and pandas_ta for technical analysis, with an RSI period and other strategy parameters defined in the configuration file.

The project supports both live operation and backtesting. The backtest result shown in the video is not presented as a finished or optimised trading system. The example produces a win rate of approximately 47% in the demonstrated test, but no parameter tuning has been performed. Results can vary significantly depending on the market, timeframe, data, trading costs, and selected parameters.

The Python platform and strategy are provided for educational purposes. Forward and backward compatibility are not guaranteed, and the code should be tested carefully before being used with a live trading account.

<!-- START_FOOTER -->

<!-- END_FOOTER -->