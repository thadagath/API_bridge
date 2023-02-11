# Trading Binance Auto Trader

Version v1.0

Last update: Feb 11th, 2023

This is boilerplate for Trading Server for Binance exchange. Currently it's only meant for trading Futures.  

## Tradingview Alert payload
Use this Pinescript boilerplate: https://www.tradingview.com/script/HwTFuzDO-Trading-Auto-Boilerplate/

And then use this text in the Alert message.

```
{
  "symbol": "ETHUSDT",
  "time": "{{timenow}}",
  "strategy": {
    "order_id": "{{strategy.order.id}}",
    "order_action": "{{strategy.order.action}}",
    "order_contracts": "{{strategy.order.contracts}}",
    "order_price": "{{strategy.order.price}}",
    "meta_data": {{strategy.order.alert_message}},
    "strategy_action": "{{strategy.order.comment}}",
    "use_limit_tp_sl": "false"
  }
}
```

You just need to update 2 things:
- `symbol`: Trading pair you want to trade, must match with your exchange's
- `use_limit_tp_sl`: `"false"` or `"true"`. This option is for who wants to use TP/SL. If it's `"false"`, the strategy will use `TAKE_PROFIT_MARKET` and `STOP_MARKET` order. If it's `"true"`, the strategy will use `TAKE_PROFIT` and `STOP` order.

## How to run the server

```
npm install
npm start
```

