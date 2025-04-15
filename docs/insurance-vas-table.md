# VAS Module: Insurance Transactions

This section allows authorized users to view insurance payment transactions based on a selected date range.

## Accessing Insurance Transactions

Navigate to **VAS Module -> Insurance Payments** (or similar link) from the main sidebar navigation[cite: 11, 25, 48, 61, 72, 86, 97, 111, 122, 136, 148, 161, 173, 186, 198, 211, 223, 247, 277, 300, 329, 343, 379, 391, 404, 416, 429].

## Features

1.  **Date Range Picker:** Select a **Start Date** and **End Date** using the calendar input field at the top left. The table will update automatically (after a brief delay) to show transactions within the selected range [cite: (Implied from component code)].
2.  **Search Filter:** Enter keywords into the search bar at the top to filter the displayed transactions across all visible columns (e.g., search by membership number, names, reference, payer cell)[cite: 34, 68, 93, 118, 143, 168, 193, 218, 255, 284, 309, 352, 386, 411, 436].
3.  **Refresh Button:** Click the refresh icon (🔄) to reload the transaction data for the currently selected date range[cite: 35, 69, 94, 119, 144, 169, 194, 219, 256, 285, 310, 353, 387, 412, 437].
4.  **Export/Download Button:** Click the download icon (📥) to export the currently filtered data shown in the table to an Excel (.xlsx) file[cite: 36, 70, 95, 120, 145, 170, 195, 220, 257, 286, 311, 354, 388, 413, 438].
5.  **Data Table:** Displays insurance transactions with the following sortable columns[cite: 37, 71, 96, 121, 146, 171, 196, 221, 258, 287, 312, 355, 389, 414, 439]:
    * **Membership #:** Policy or membership number associated with the payment.
    * **Names:** Name(s) of the policyholder.
    * **Product:** Type of insurance product (e.g., Funeral, Investment).
    * **Reference:** Unique transaction reference number.
    * **Paid Amount:** Total amount paid (including fees, prefixed with 'M').
    * **Paid By Device:** Name associated with the payment device or agent.
    * **Payer Cell:** Cell number of the payer/agent (displays with a phone icon).
    * **Payer Type:** Type of payer (e.g., Merchant).
    * **Date:** Date the transaction occurred (format YYYY-MM-DD).
    * *(Other columns like Amount Due, Fee, Agent ID, Base Amount, Months, Paid By ID might be available but hidden by default)*
6.  **Pagination:** Use the controls at the bottom to navigate through pages if there are more transactions than fit on one page. You can also change the number of items displayed per page[cite: 41, 42, 43, 262, 263, 264, 291, 292, 293, 316, 317, 318, 359, 360, 361].

## API Interaction

* **Endpoint:** `POST /api/marketing/insurance`
* **Request Body:** `{ "from_date": "YYYY-MM-DD", "to_date": "YYYY-MM-DD" }`
* **Authentication:** Requires Bearer token.
* **Response:** An array of insurance transaction objects matching the specified date range.