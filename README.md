# **Data Analysis on E-Commerce and its Delivery partner charges.**

#### **SQL database dump is in ```CoinTab.sql``` file above. Download CoinTab.sql file to your local computer and import it to MySql server**

## **Data Analysis in SQL**
 
1. Select the cointab database as default database

```
USE CoinTab;
```
2. Join the tables

```
SELECT i.AWB_Code , i.Order_ID,  o.SKU_No, o.Order_Qty, s.Weight_g as ActualWeight,  i.Charged_Weight ,
 i.Warehouse_Pincode, i.Customer_Pincode, i.zone, i.Type_of_Shipment, i.Courier_rate, i.Billing_Amount, r.Rate
FROM order_report as o
INNER JOIN invoice as i
On i.Order_ID = o.ExternOrderNo 
INNER JOIN sku_master as s
On o.SKU_No = s.SKU_No
INNER JOIN rates as r
On i.Courier_rate = r.Courier_rate ;
```

3. Now export the result as a cvs file.

## **Data Analysis using python**

#### **Required Installments**

1. Pandas
2. Numpy

#### Load ```ConsolidatedData.csv``` file in ```CoinTab Assignment.ipynb``` 

## **BI report file -> ```Cointab.pbix``` has also been included.**

 
