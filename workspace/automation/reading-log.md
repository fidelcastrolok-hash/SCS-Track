# Reading log -- SCS3.5

Script: workspace/automation/check-stock.gs
Read to the last line before the first run: yes
Label: AI-assisted, directed by fisher

| Line no. | The line, first words | In my own words | Which word |
|---|---|---|---|
| 4 | `function checkstock(){` | Defines the main function named checkstock | trigger |
| 5 | `const ss = SpreadsheetApp.getActiveSpreadsheet();` | Gets the currently open Google Sheet | variable |
| 6 | `const dashboard = ss.getSheetByName("DASHBOARD");` | Selects the DASHBOARD tab | variable |
| 7 | `if (!dashboard) return;` | Stops the script safely if the DASHBOARD tab is missing | condition |
| 8-9 | `const StockData = dashboard.getRange("A12:C15").getValues();` | Reads rows 12 to 15 across columns A to C into a list | variable |
| 10 | `const lowStockItems =StockData.filter ( row => row[2]=== "REORDER");` | Keeps only the rows where column C equals REORDER | loop |
| 11 | `let reminders = ss.getSheetByName("REMINDERS");` | Looks for a tab named REMINDERS | variable |
| 12 | `if (!reminders) {` | Checks if the REMINDERS tab does not exist yet | condition |
| 13 | `reminders = ss.insertSheet ("REMINDERS");` | Creates a new tab named REMINDERS | sequence |
| 15 | `reminders.clearContents();` | Clears all existing values on the REMINDERS tab | sequence |
| 16 | `reminders.getRange("A1:C1").setValues ([["ITEM", "CURRENT STOCK", "STATUS"]]);` | Writes the three column headers in row 1 of REMINDERS | sequence |
| 17 | `if (lowStockItems.length > 0 ) {reminders.getRange(2, 1, lowStockItems.length, 3).` | Checks if any items need reordering and selects the destination rows on REMINDERS | condition |
| 18 | `setValues(lowStockItems);` | Writes the filtered reorder items into those selected rows | sequence |
