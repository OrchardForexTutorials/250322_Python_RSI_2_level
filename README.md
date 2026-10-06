# Python RSI 2 Level Strategy

<!-- START_HEADER -->
Youtube:  
https://youtu.be/A7NEHRM9VnE

For a broker with fast execution and tight spreads sign up to IC Markets using our affiliate link <br>
https://orchardforex.com/ic
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
### Warning

This is not to be used for live trading

### License

The project is released under [GNU GPLv3 licence](https://www.gnu.org/licenses/quick-guide-gplv3.html),
so that means the software is copyrighted, however you have the freedom to use, change or share the software
for any purpose as long as the modified version stays free. See: [GNU FAQ](https://www.gnu.org/licenses/gpl-faq.html).

You should have received a copy of the GNU General Public License along with this program
(check the [LICENSE] file).
If not, please read <http://www.gnu.org/licenses/>.
For simplified version, please read <https://tldrlegal.com/license/gnu-general-public-license-v3-(gpl-3)>.

## Terms of Use

By using this software, you understand and agree that we (company and author)
are not be liable or responsible for any loss or damage due to any reason.
Although every attempt has been made to assure accuracy,
we do not give any express or implied warranty as to its accuracy.
We do not accept any liability for error or omission.

You acknowledge that you are familiar with these risks
and that you are solely responsible for the outcomes of your decisions.
We accept no liability whatsoever for any direct or consequential loss arising from the use of this product.
You understand and agree that past results are not necessarily indicative of future performance.

Use of this software serves as your acknowledgement and representation that you have read and understand
these TERMS OF USE and that you agree to be bound by such Terms of Use ("License Agreement").

### Copyright information

Copyright © 2013-2022 - Novateq Pty Ltd - All Rights Reserved

### Disclaimer and Risk Warnings

Trading any financial market involves risk.
All forms of trading carry a high level of risk so you should only speculate with money you can afford to lose.
You can lose more than your initial deposit and stake.
Please ensure your chosen method matches your investment objectives,
familiarize yourself with the risks involved and if necessary seek independent advice.

NFA and CTFC Required Disclaimers:
Trading in the Foreign Exchange market as well as in Futures Market and Options or in the Stock Market
is a challenging opportunity where above average returns are available for educated and experienced investors
who are willing to take above average risk.
However, before deciding to participate in Foreign Exchange (FX) trading or in Trading Futures, Options or stocks,
you should carefully consider your investment objectives, level of experience and risk appetite.
**Do not invest money you cannot afford to lose**.

CFTC RULE 4.41 - HYPOTHETICAL OR SIMULATED PERFORMANCE RESULTS HAVE CERTAIN LIMITATIONS.
UNLIKE AN ACTUAL PERFORMANCE RECORD, SIMULATED RESULTS DO NOT REPRESENT ACTUAL TRADING.
ALSO, SINCE THE TRADES HAVE NOT BEEN EXECUTED, THE RESULTS MAY HAVE UNDER-OR-OVER COMPENSATED FOR THE IMPACT,
IF ANY, OF CERTAIN MARKET FACTORS, SUCH AS LACK OF LIQUIDITY. SIMULATED TRADING PROGRAMS IN GENERAL
ARE ALSO SUBJECT TO THE FACT THAT THEY ARE DESIGNED WITH THE BENEFIT OF HINDSIGHT.
NO REPRESENTATION IS BEING MADE THAN ANY ACCOUNT WILL OR IS LIKELY TO ACHIEVE PROFIT OR LOSSES SIMILAR TO THOSE SHOWN.
<!-- END_FOOTER -->