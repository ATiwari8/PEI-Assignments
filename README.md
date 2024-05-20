# PEI-Assignments

Please refer the above PBIX file- Assignment.pbix.

**Data Modelling**: The shipment table does not contain order ID, so to get the shipment of an order, I have assumed FIFO (First In First Out) logic (First Order First Shipment) for customer as Customer ID is present in both the tables. Since we don't have order date and shipment date, I have considered order ID and Shipment ID for FIFO. I have created the calculated columns to get the customer shipments ranks and customer order ranks, and using them connected the Order and Shipping tables to the get shipment status for an order.

Also, I have connected the Customer table and Order table with 1:M cardinality using customer id.

**Data Catalog**: Below are the steps applied for data catalog and cleansing in Power Query:
1. Changed the data types of all columns of the tables.
2. Removed the extra spaces if any in the Name and Last Name from customer.
3. Created a custom column to get the Full Name of customer from first and last name.
4. Extracted only the characters from Full Name and checked if it contain special characters expect Space.
5. Replaced those special characters with valid characters and removed the extra columns created for check of valid name.
6. Also found out the price of Mousepad is 200 and 250 for the orders in same country and same customer. All others products are having unique price. Assuming the there are two categories of mouse, kept the both prices in the dataset.

 Please find few insights apart from the insights of the visuals:
 
1. UK and USA are having major contribution in global net sales with 45.9% and 44.7% respectively.
2. Above 40 age group contributes 75% in USA, 53% in UK and 60% in UAE net sales.
3. Monitor and Hard Disk are two top contributors with 56.3% and 23.5% in global net sales.
4. Hard Disk contributes 40% of UAE net sales, Monitor contributes 63.8% and 55.4% of net sales of UK and US respectively.  
5. As per FIFO logic, only 15% of UAE orders and 16% of both UK and US orders are delivered.
