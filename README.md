# Excel Data Pipeline

Enterprise Excel data processing pipeline built with Java and Apache POI.

This project demonstrates how to design a reliable Excel data processing system for enterprise environments.

---

## Architecture

Excel Upload  
↓  
Apache POI Parsing  
↓  
Header Mapping  
↓  
Data Validation  
↓  
Database Insert  

---

## Problem

Enterprise systems often rely on Excel files for bulk data input.  
However, Excel data typically contains issues such as:

- inconsistent column headers
- merged cells
- invalid data formats
- manual data errors

These issues can cause unstable data processing pipelines.

---

## Solution

This project demonstrates a structured Excel processing pipeline:

1. Excel file upload
2. Apache POI based parsing
3. Dynamic header mapping
4. Data validation
5. Database insertion

---

## Key Features

### Excel Parsing

Uses **Apache POI** to read Excel files and extract structured data.

### Header Mapping

Supports dynamic column mapping so that column order does not affect processing.

### Data Validation

Validates:

- required fields
- numeric values
- duplicate rows

### Database Insert

Validated data is inserted into database tables using batch processing.

---

## Technologies

- Java
- Apache POI
- Spring Boot
- MySQL

---

## Example Code

```java
Workbook workbook = WorkbookFactory.create(file);
Sheet sheet = workbook.getSheetAt(0);

for (Row row : sheet) {
    Cell cell = row.getCell(0);
    String value = cell.getStringCellValue();
}
