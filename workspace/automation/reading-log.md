# Reading log -- SCS3.5

Script: workspace/automation/check-stock.gs
Read to the last line before the first run: yes
Label: AI-assisted, directed by fisher

| Line no. | The line, first words | In my own words | Which word |
|---|---|---|---|
| 4 | `function checkstock(){` | Defines the main function named checkstock | trigger |
| 5 | `const ss = SpreadsheetApp.getActiveSpreadsheet();` | Gets the currently open Google Sheet | variable |
| 6 | `const dashboard = ss.getSheetByName("DASHBOARD");` | Selects the DASHBOARD tab | variable |
| 7-8 | `const StockData = dashboard.getRange("A12:C15").getValues();` | Reads rows 12 to 15 across columns A to C into a list | variable |
| 9 | `const lowStockItems =StockData.filter ( row => row[2]=== "REORDER");` | Keeps only the rows where column C equals REORDER | loop |
| 10 | `let reminders = ss.getSheetByName("REMINDERS");` | Looks for a tab named REMINDERS | variable |
| 11-12 | `if (!reminders) { reminders = ss.insertSheet ("REMINDERS");` | Creates the REMINDERS tab if it does not exist yet | condition |
| 14 | `reminders.clearContents();` | Clears all existing values on the REMINDERS tab | sequence |
| 15 | `reminders.getRange("A1:C1").setValues ([["ITEM", "CURRENT STOCK", "STATUS"]]);` | Writes the three column headers in row 1 of REMINDERS | sequence |
| 16-17 | `if (lowStockItems.length > 0 ) {reminders.getRange(2, 1, lowStockItems.length, 3).setValues(lowStockItems);` | If any items need reordering, writes them starting at row 2 of REMINDERS | condition |