## E-commerce Order Analysis and Verification

### Business Scenario

X receives thousands of orders daily through their website and collaborates with multiple courier companies for order deliveries. These courier companies charge X based on two factors: the weight of the products and the distance between X's warehouse (pickup location) and the customer's delivery address (destination location). On average, the delivery charge is approximately Rs. 100 per shipment. Given that X ships around 1,00,000 orders per month, they incur significant monthly expenses, and they want to ensure the accuracy of these charges levied by their courier partners.

### Input Data

**Left-Hand Side (LHS) Data (X's internal data spread across three reports):**

1. **Website Order Report:** This report contains Order IDs and various products (SKUs) included in each order. The Order ID is a common identifier between X's order report and the courier company's invoice.

2. **SKU Master:** This data includes the gross weight of each product. It is used to calculate the total weight of each order and to compare it against the weight reported by the courier company in their CSV invoice. The courier company calculates weight in slabs of 0.5 KG multiples, so you must determine the total weight of the shipment and applicable weight slabs.

3. **Warehouse Pincode to All India Pincode Mapping:** This mapping is used to determine the delivery zone (a/b/c/d/e) and to compare it against the information reported by the courier company in their CSV invoice per Order ID.

**Right-Hand Side (RHS) Data (courier company invoice in CSV file):**

The courier company's invoice in CSV format contains the following fields:

- AWB Number (courier company’s internal ID)
- Order ID (X's order ID)
- Weight of shipment
- Warehouse pickup pincode
- Customer delivery pincode
- Zone of delivery
- Charges per shipment
- Type of shipment

The invoice also includes the courier charges rate card at weight slab and pincode level. The type of shipment (Forward charges or Forward and RTO charges) determines the applicable charges based on zones and fixed and additional weights according to weight slabs.

For the first 0.5 KG, a "fixed" rate is applicable. For each additional 0.5 KG, an "additional" weight charge in the same proportion is applicable. The total charges will be the sum of the "fixed" and "total additional" charges, if any.

### Output Data 1

The goal is to create a resultant CSV file with the following columns:

![image](https://github.com/Nasir151/Microsoft-Excel-Projects/assets/94509995/fa812f0e-61e4-41f1-aac2-e1c850f4ceb5)

### Output Data 2
Create a summary table

![image](https://github.com/Nasir151/Microsoft-Excel-Projects/assets/94509995/c821f9c1-80f2-4d43-b936-94b2c14e839b)

