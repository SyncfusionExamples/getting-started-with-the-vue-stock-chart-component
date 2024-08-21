<script setup>
import {StockChartComponent as EjsStockchart, CandleSeries,
StockChartSeriesCollectionDirective as EStockchartSeriesCollection,
StockChartSeriesDirective as EStockchartSeries, 
DateTime, LineSeries, SplineSeries, HiloOpenCloseSeries,
HiloSeries, RangeAreaSeries,Trendlines, EmaIndicator,
RsiIndicator, BollingerBands, TmaIndicator,
MomentumIndicator, SmaIndicator, AtrIndicator, 
AccumulationDistributionIndicator, MacdIndicator, 
StochasticIndicator, Export, Crosshair, Tooltip
} from '@syncfusion/ej2-vue-charts';
import {chartData} from './data';
import {provide} from 'vue';
provide('stockChart',[CandleSeries,DateTime, LineSeries, 
SplineSeries, HiloOpenCloseSeries, HiloSeries, 
RangeAreaSeries,Trendlines, EmaIndicator,
RsiIndicator, BollingerBands, TmaIndicator,
MomentumIndicator, SmaIndicator, AtrIndicator, 
AccumulationDistributionIndicator, MacdIndicator, 
StochasticIndicator, Export, Crosshair, Tooltip]);
const crosshair = {enable: true, lineType: 'Both'};
const primaryXAxis = {
  crosshairTooltip: {enable: true}
};
const tooltip = {enable: true};
const enableSelector = false;
const periods = [{
  selected: true,
  intervalType: 'Hours',
  interval: 12,
  text: '12H'
}];
const enablePeriodSelector = false;
</script>

<template>
<ejs-stockchart height="500px" width="900px"
title="Stock Price Analysis" :crosshair="crosshair"
:primaryXAxis="primaryXAxis" :tooltip="tooltip"
:enableSelector="enableSelector" :periods="periods"
:enablePeriodSelector="enablePeriodSelector">
<e-stockchart-series-collection>
  <e-stockchart-series type="Candle" :dataSource="chartData"
  xName="x">
  </e-stockchart-series>
</e-stockchart-series-collection>
</ejs-stockchart>
</template>

<style scoped>

</style>
