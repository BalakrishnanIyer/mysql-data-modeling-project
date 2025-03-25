# RC_Model_Company_Database

This repository contains the database schema and business rules for the RC Models Company, which specializes in customizable products with various decals and handles vendor, customer, and order management.

## 📁 Contents

- `RD_Model.mwb`: MySQL Workbench model file.
- `Team 11_Business Rules Doc.docx`: Business rules and entity relationships.
- `assignment_5.pdf`: Entity schema reference.

## 🧱 Entities and Attributes

### Product
- `Product_ID` (PK)
- `Product_Desc`
- `Vendor_ID` (FK)
- `Category`
- `Price`
- `Availability`

### Decals
- `Decal_ID` (PK)
- `Decal_Desc`
- `Product_ID` (FK)

### Product Backorder
- `ProductBO_ID` (PK)
- `Product_ID` (FK)
- `Customer_ID` (FK)

### Customer
- `Customer_ID` (PK)
- `Name`
- `Contact`
- `Customer_CC`
- `Payment_Info`
- `Potential_Customers_Name`

### Invoice
- `Invoice_ID` (PK)
- `Customer_ID` (FK)
- `Product_ID`
- `Shipping_Charge`
- `Product_Price`
- `Tax`
- `Decal_ID`

### Inventory
- `Inventory_ID` (PK)
- `Product_ID` (FK)
- `Decal_ID` (FK)
- `Units`
- `Price_Per_Unit`
- `QOH` (Quantity on Hand)
- `Min_QOH_Req`

### Promotions
- `Promotions_ID` (PK)
- `Customer_ID` (FK)

### Reports
- `Report_ID` (PK)
- `Customer_ID`
- `Product_ID` (FK)
- `Product_Weekly_TO`
- `Weekly_Rev_by_Product`
- `Week No`

### Website Traffic
- `Cookie_ID` (PK)
- `Customer_ID` (FK)
- `Date`
- `Time_spent_in_min`

### Subscriptions
- `Potential_customer_ID` (PK)
- `Customer_ID` (FK)
- `Potential_customer_name`
- `Potential_customer_email`
- `Potential_customer_number`

### Vendor
- `Vendor_ID` (PK)
- `Vendor_name`
- `Website_Link`
- `Product_ID` (FK)
- `Decal_ID` (FK)
- `Potential_Vendor_ID`

### Vendor Order
- `Vendor_Order_ID` (PK)
- `Date`
- `Transaction_ID`
- `Product_ID` (FK)
- `Decal_ID` (FK)
- `Shipping_cost`

## 📌 Business Rules & Assumptions

- A product can have multiple decals, vendors, and appear in reports and backorders.
- Customers can generate multiple invoices and have multiple credit cards.
- Potential customers must not have generated invoices.
- Invoices can include multiple products and decals.
- Orders can be placed only if a product is unavailable (backorder).
- Decals are unique to a product.
- Inventory items not sold in 4 weeks are scrapped.
- Reports show weekly product turnover and revenue.
- All transactions are processed via credit card.

## 🛠 Tools

- **MySQL Workbench**: Database modeling.
- **Word/Docs**: Documentation of business rules and entity relationships.

