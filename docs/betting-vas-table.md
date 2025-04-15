# VAS Module: Betting Transactions

This section allows authorized users to view betting transactions processed through the platform, filtered by a specific date.

## Accessing Betting Transactions

Navigate to **VAS Module -> Betting Transactions** (or similar link) from the main sidebar navigation[cite: 11, 25, 48, 61, 72, 86, 97, 111, 122, 136, 148, 161, 173, 186, 198, 211, 223, 247, 277, 300, 329, 343, 379, 391, 404, 416, 429].

## Features

1.  **Date Picker:** Use the calendar input field at the top left to select a specific date. The table will automatically fetch and display transactions for the chosen date [cite: (Implied from component code)].
2.  **Search Filter:** Enter keywords into the search bar at the top to filter the displayed transactions across all visible columns (e.g., search by name, cell, reference, location)[cite: 34, 68, 93, 118, 143, 168, 193, 218, 255, 284, 309, 352, 386, 411, 436].
3.  **Refresh Button:** Click the refresh icon (🔄) to reload the transaction data for the currently selected date[cite: 35, 69, 94, 119, 144, 169, 194, 219, 256, 285, 310, 353, 387, 412, 437].
4.  **Export/Download Button:** Click the download icon (📥) to export the currently filtered data shown in the table to an Excel (.xlsx) file[cite: 36, 70, 95, 120, 145, 170, 195, 220, 257, 286, 311, 354, 388, 413, 438].
5.  **Data Table:** Displays betting transactions with the following sortable columns[cite: 37, 71, 96, 121, 146, 171, 196, 221, 258, 287, 312, 355, 389, 414, 439]:
    * **Name:** Payer's first name.
    * **Surname:** Payer's last name.
    * **Cell:** Payer's cell number (displays with a phone icon).
    * **Amount:** Transaction amount (prefixed with 'M').
    * **Commission:** Commission earned (prefixed with 'M').
    * **Location:** Betting provider (e.g., Gbets, eBet).
    * **Reference:** Unique transaction reference number.
    * **Type:** Transaction type (e.g., DEPOSIT shown in green, CREDIT shown in purple).
    * **Date:** Full date and timestamp of the transaction.
    * *(Other columns like Business Name, Last Amount might be available but hidden by default)*
6.  **Pagination:** Use the controls at the bottom to navigate through pages if there are more transactions than fit on one page. You can also change the number of items displayed per page[cite: 41, 42, 43, 262, 263, 264, 291, 292, 293, 316, 317, 318, 359, 360, 361].

## API Interaction

* **Endpoint:** `POST /api/marketing/betting`
* **Request Body:** `{ "date": "YYYY-MM-DD" }`
* **Authentication:** Requires Bearer token.
* **Response:** An array of transaction objects matching the specified date.