# Project Steps

## 1. Load Excel Data
- Open the `ExcelAndClean.xaml` sequence.
- Read the input Excel file.
- Perform initial cleaning and formatting of the data.
- Store the cleaned results in a `DataTable` variable (`dtExcel`).

## 2. Call the API
- Use the HTTP Request activity.
- Send request to the API endpoint.
- Save the response into a variable (e.g., `apiXmlOut`).
- Deserialize the XML response into a `DataSet` or `DataTable`.

## 3. Compare Excel Data with API Data
- Use a `For Each Row` loop on the Excel `DataTable`.
- Check if each record exists in the API `DataTable`.
- Collect mismatches in a `conflicts` DataTable.

## 4. Generate Report of Missing Records
- Filter records from Excel that are **not present** in the API response.
- Add these missing records into a new `DataTable` (e.g., `dtMissing`).
- Write `dtMissing` to an output Excel file (`MissingRecords.xlsx`).

## 5. Final Outputs
- `dtExcel` → Cleaned input data from Excel.
- `apiXmlOut` / `dtAPI` → Data received from API.
- `dtMissing` → List of records missing in API.
- Exported Excel report for business review.
