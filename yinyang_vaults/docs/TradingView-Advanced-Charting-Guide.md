# TradingView Advanced Charting Library: Custom Theme Candle Colors

## 1. Get the Library
- Request a free license for open-source/non-commercial use or purchase a commercial license: [TradingView Charting Library](https://www.tradingview.com/HTML5-stock-forex-bitcoin-charting-library/)
- Download the library package from TradingView after approval.

## 2. Add to Your Web Project
- Unzip the library and copy the `charting_library` folder into your project (e.g., `public/charting_library/`).
- Include the library in your HTML:
  ```html
  <script src="/charting_library/charting_library.js"></script>
  ```

## 3. Basic Chart Setup
```js
const widget = new TradingView.widget({
  symbol: 'BINANCE:BTCUSDT',
  interval: '15',
  container_id: 'tv_chart_container',
  library_path: '/charting_library/',
  theme: 'Dark',
  overrides: {
    'mainSeriesProperties.candleStyle.upColor': '#ff4444', // HEAT color
    'mainSeriesProperties.candleStyle.downColor': '#00aaff', // O color
    'mainSeriesProperties.candleStyle.borderUpColor': '#ff4444',
    'mainSeriesProperties.candleStyle.borderDownColor': '#00aaff',
  },
  // ...other config...
});
```

## 4. Dynamic Theme Switching
To change candle colors when the user flips between O/HEAT:
```js
function setCandleColors(isHeat) {
  widget.applyOverrides({
    'mainSeriesProperties.candleStyle.upColor': isHeat ? '#ff4444' : '#00aaff',
    'mainSeriesProperties.candleStyle.downColor': isHeat ? '#00aaff' : '#ff4444',
    'mainSeriesProperties.candleStyle.borderUpColor': isHeat ? '#ff4444' : '#00aaff',
    'mainSeriesProperties.candleStyle.borderDownColor': isHeat ? '#00aaff' : '#ff4444',
  });
}
// Call setCandleColors(true) for HEAT, setCandleColors(false) for O
```

## 5. Integration Tips
- Place the chart in a responsive container.
- Use your UI's theme state to call `setCandleColors` on flip.
- You can override many other chart colors for full theme integration.

## 6. Resources
- [TradingView Charting Library Docs](https://tradingview.github.io/lightweight-charts/)
- [Charting Library FAQ](https://www.tradingview.com/HTML5-stock-forex-bitcoin-charting-library/)
- [Widget Color Overrides Reference](https://tradingview.github.io/lightweight-charts/docs/customization)

---
*This guide helps you fully theme your TradingView chart for Fuego Forecast's O/HEAT modes.* 