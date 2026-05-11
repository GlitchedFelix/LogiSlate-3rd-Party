# Logistics Processor V4.7

_AI-assisted Excel data filtering, sorting, and fuzzy grouping system._

## Overview

Logistics Processor V4.7 is a web-based tool designed to automate the cleaning, grouping, and preparation of logistics manifest data for invoicing, with a user-friendly drag-and-drop interface. It leverages AI-inspired string similarity algorithms and Excel processing libraries. All processing happens entirely in your browser—no data uploads to external servers.

![Screenshot](https://user-images.githubusercontent.com/your-image-path-here) <!-- Replace with an actual screenshot if available -->

---

## Features

- **Excel (.xlsx) manifest upload via drag-and-drop or click**
- **Automatic data cleaning and normalization**
  - Date normalization
  - Duplicate removal using smart reference cleaning
- **Intelligent grouping and fuzzy matching**
  - Group by customer, address, and delivery date using advanced string similarity
  - Special logic for Inter-Branch Transfers (IBT)
- **Downloadable processed Excel output**
  - Separate output sheets per delivery company
- **Manifest Excel template download for easy onboarding**
- **100% client-side for privacy and speed**

---

## Usage

### 1. Open the Application

Open [`index.html`](./index.html) in your browser.

### 2. Download the Manifest Template (Optional)

Click the **"Download Template"** button to download a correctly formatted `.xlsx` file. Fill in your logistics data as shown in the sample.

**Expected columns:**
- Booking_Date
- Shipper_Ref
- ID
- Customer
- To_Location
- Delivery_Distance
- Delivery_Weight
- Sending_Store
- Receiving_Store
- Driver_Address

### 3. Upload Your Manifest

1. **Drag and drop** your `.xlsx` file onto the "Drop Manifest Here" area, or click the area to select a file.
2. Wait for the file to load; the log panel will show progress.

### 4. Process the Data

- Press the **"Generate Processed File"** button after upload.
- The system will:
  - Normalize dates and clean IDs
  - Remove duplicates
  - Group similar deliveries/fuzzy-match addresses and customers
  - Create separate sheets by delivery company
- Download of the processed Excel file (`Logistics_Output_Final.xlsx`) will begin automatically.

### 5. Review & Use Output

The final Excel file will contain:
- A **raw data** sheet (as loaded)
- One sheet per delivery company, containing grouped and cleaned deliveries
  - Grouping explanations and confidence scores provided for each record

---

## Example Workflow

1. Download and fill out `Upload_Template.xlsx`.
2. Upload filled manifest using the web page.
3. Click "Generate Processed File."
4. Receive `Logistics_Output_Final.xlsx` with grouped and cleaned deliveries.

---

## How It Works

- Uses [SheetJS (xlsx)](https://github.com/SheetJS/sheetjs) for reading Excel files.
- Uses [ExcelJS](https://github.com/exceljs/exceljs) for writing multi-sheet Excel outputs.
- Fuzzy grouping performed with bigram string similarity (customers, addresses).
- Groups deliveries on matching dates and similar characteristics.
- All logic is implemented in client-side JavaScript (see [`index.html`](./index.html)).

---

## Tech Stack

- HTML5
- JavaScript (ES6)
- [Bootstrap 5](https://getbootstrap.com/) (for UI)
- [SheetJS (xlsx)](https://github.com/SheetJS/sheetjs)
- [ExcelJS](https://github.com/exceljs/exceljs)

---

## License

This project is licensed under the [MIT License](./LICENSE).

&copy; 2026 GlitchedDesigns. All rights reserved.

---

## Contributing

Pull requests and suggestions welcome! Please create an issue or PR for any improvements.

---

## FAQ

### Will my data be uploaded or shared?
**No.** All processing runs entirely in your browser for privacy and security.

### Can I use CSV files?
Currently, only Excel files (`.xlsx` or `.xls`) are supported.

### Can I customize grouping logic?
Advanced users may edit the JavaScript in [`index.html`](./index.html) to adjust grouping thresholds or add logic.

---

## Support

For questions, issues, or feature requests, please open an [issue on GitHub](https://github.com/GlitchedFelix/Logistics_Processor/issues).
