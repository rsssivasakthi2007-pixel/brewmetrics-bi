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