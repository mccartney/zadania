 Introduction
==============

Below you can find a description of a simple database (consisting of a few tables) and the scope of the data (query) that is needed.

 Data structure
================
The table ```WAREHOUSE``` lists warehouses in the system.
The table ```ITEM``` is used to store item data. An item is assigned to a specific warehouse (by ```warehouse_id```). An item can be active (Y) or inactive (N).
The table ```FORECASTING``` holds current forecasting values for items, like estimate of demand (eod), total forecast, trend and standard deviation. Each of the items has a corresponding entry in forecasting table (```forecasting.id=item.id```).
The table ```FORECASTING_HIST``` holds past and future forecasts for items. Forecasts history is stored for a specific month and item. Forecast_date is equal to first day of a month for which this forecast is valid. Forecast for item 7 and month of January 2013, is designated by ```item_id=7``` and ```forecast_date = '20130101'```. 

Sample database can be created using ```create_test_db.sql```.

 Goal
======

Prepare SQL query for item parameters export. The export should contain the following values:
- warehouse code,
- item code,
- unit cost,
- currency,
- estimate of demand (EOD),
- current total forecast
- a list of future forecasts for next 6 months. This list should be separated by semicolons and enclosed within squaaree brackets.

The export should be generated only for active items.
The export should take as a parameter start date for the list of forecasts.


 Sample output
===============
On sample data the export for ```20130901``` should give the following output:

```
WAREHOUSE_CODE                   ITEM_CODE                        UNIT_COST CURRENCY                              EOD TOT_FORECAST FUTURE_FORECAST
-------------------------------- -------------------------------- --------- -------------------------------- -------- ------------ ------------------------------------------------------------------
WARSAW                           ITEM01                                2.45 PLN                                8.4511      12.4567 [69.5995;71.8853;74.1709;76.4567;78.7425;81.0281]
WARSAW                           ITEM02                              313.47 PLN                               999.999      1345.54 [1405.54;1407.04;1408.54;1410.04;1411.54;1413.04]
STOCKHOLM                        ITEM01                              123.45 EUR                                 8.056         79.9 [153.2333;154.5667;155.9;157.2333;158.5667;159.9]
STOCKHOLM                        ITEM02                              555.57 SEK                                     0            0 [0;0;0;0;0;0]
TOKYO                            ITEM01                            12345.78 JPY                               555.056         7.89 [91.89;93.09;94.29;95.49;96.69;97.89]
TOKYO                            ITEM03                            55555.57 JPY                                     0           80 [179.1667;180.3333;181.5;182.6667;183.8333;185]
```

 SQL / Database
================

It's advised to work towards an Oracle database.
