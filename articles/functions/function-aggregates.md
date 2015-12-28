<properties
	pageTitle="PowerApps: Average, Max, Min, StdevP, Sum, and VarP functions"
	description="Reference information for the Average, Max, Min, StdevP, Sum, and VarP functions in PowerApps, including syntax and examples"
	services=""
	suite="powerapps"
	documentationCenter="na"
	authors="gregli-msft"
	manager="dwrede"
	editor=""
	tags=""/>

<tags
   ms.service="powerapps"
   ms.devlang="na"
   ms.topic="article"
   ms.tgt_pltfrm="na"
   ms.workload="na"
   ms.date="11/07/2015"
   ms.author="gregli"/>

# Average, Max, Min, StdevP, Sum, and VarP functions in PowerApps #

Aggregate functions that summarize a set of numbers.

## Description ##

The **Average** function calculates the average, or arithmetic mean, of its arguments.

The **Max** function finds the maximum value.

The **Min** function finds the minimum value.

The **Sum** function calculates the sum of its arguments.

The **StdevP** function calculates the standard deviation of its arguments.

The **VarP** function calculates the variance of its arguments.

You can supply the values for these functions as:

- Separate arguments. For example, **Sum( 1, 2, 3 )** returns 6.
- A [table](working-with-tables.md) and a formula to operate over that table.  The aggregate will be calculated on the values of the formula for each [record](working-with-tables.md#records).  The formula can reference [columns](working-with-tables.md#columns) in the table.  

These functions operate on numeric values only. Other types of values, such as strings or records, are ignored. Use the **[Value](function-value.md)** function to convert a string into a number.

## Syntax ##

**Average**( *NumericalFormula1*, [ *NumericalFormula2*, ... ] )<br>**Max**( *NumericalFormula1*, [ *NumericalFormula2*, ... ] )<br>**Min**( *NumericalFormula1*, [ *NumericalFormula2*, ... ] )<br>**Sum**( *NumericalFormula1*, [ *NumericalFormula2*, ... ] )<br>**StdevP**( *NumericalFormula1*, [ *NumericalFormula2*, ... ] )<br>**VarP**( *NumericalFormula1*, [ *NumericalFormula2*, ... ] )

- *NumericalFormula(s)* - Required.  Numeric values to operate on.

**Average**( *Table*, *NumericalFormula* )<br>**Max**( *Table*, *NumericalFormula* )<br>**Min**( *Table*, *NumericalFormula* )<br>**Sum**( *Table*, *NumericalFormula* )<br>**StdevP**( *Table*, *NumericalFormula* )<br>**VarP**( *Table*, *NumericalFormula* )

- *Table* - Required.  Table to operate on.
- *NumericalFormula* - Required. Formula to evaluate for each record. The result of this formula is used for the aggregation. You can use columns of the table in the formula.

## Examples ##

### Step by step ###

Let's say that you had a [data source](working-with-data-sources.md) named **Sales** that contained a **CostPerUnit** column and a **UnitsSold** column, and you set the **Text** property of a label to this function:<br>
**Sum(Sales, CostPerUnit * UnitsSold)**

The label would show total sales by multiplying the values in those columns for each record and then adding the results from all records together:<br>![Calculate total sales from units sold and cost per unit](./media/function-aggregates/total-sales.png)

As a different example, let's say that you had sliders that were named **Slider1**, **Slider2**, and **Slider3** and a label with its **Text** property set to this formula:<br>
**Sum(Slider1!Value, Slider2!Value, Slider3!Value)**

The label would show the sum of all values to which the sliders were set.