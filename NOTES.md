# Copilot-Assisted DAX Development

## Measure 1: MoM Sales Growth %

### Copilot suggestion
Copilot suggested a DAX measure that compares current month sales with the previous month's sales using DATEADD and the Dim_Date date table.

### My correction
I reviewed the generated DAX and verified that it correctly uses the existing Total Sales measure and Dim_Date[date]. No correction was required.

### Final DAX

MoM Sales Growth % =
VAR CurrentSales = [Total Sales]
VAR PreviousMonthSales =
    CALCULATE(
        [Total Sales],
        DATEADD('Dim_Date'[date], -1, MONTH)
    )
RETURN
    DIVIDE(CurrentSales - PreviousMonthSales, PreviousMonthSales)
## Measure 2: Running Total Sales

### Copilot suggestion
Copilot suggested a running total measure using the existing Total Sales measure, the Dim_Date date table, MAX to identify the current date, and ALLSELECTED to accumulate sales within the selected date range.

### My correction
I reviewed the generated DAX and verified that it correctly accumulates sales from the beginning of the selected date range through the current date. No correction was required.

### Final DAX

Running Total Sales =
VAR CurrentDate = MAX('Dim_Date'[date])
RETURN
    CALCULATE(
        [Total Sales],
        FILTER(
            ALLSELECTED('Dim_Date'),
            'Dim_Date'[date] <= CurrentDate
        )
    )