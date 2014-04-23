
 


| API Call | Available Parameters |
| --- | --- | 
| Get Products | /jsonservice/v1/products/

&productid=[ID of product] OR &productcode=[Code of product] 

&limit=[Integer] 

&fields=[name of field1, name of field2, ...] 

&live=[0 OR 1] |
| Create New Order: create an empty order. | /jsonservice/v1/neworder/

No parameters. |


Get Order 
 /jsonservice/v1/order/
&orderid=[ID of order]
Delete Order 
 /jsonservice/v1/deleteorder/
&orderid=[ID of order]
Clear Order : remove all items from order. 
 /jsonservice/v1/clearorder/
&orderid=[ID of order]
Remove Item from Order 
 /jsonservice/v1/orderdeleteitem/
&orderid=[ID of order] 
 &orderitemid=[ID of order item]
Get Availability 
 /jsonservice/v1/availability/
&productid=[ID of product] OR &productcode=[Code of product] 
 &date=[date : YYYY-MM-DD] (today by default)
Add Item to Oder 
 /jsonservice/v1/orderadditem/
&orderid=[ID of order] 
 &productvariation=[ID of price variation] 
 &quantity=[Quantity of the item] (1 by default) 
 &eventid=[ID of event]
Complete Order 
 /jsonservice/v1/completeorder/
&orderid=[ID of order]
Create New Customer 
 /jsonservice/v1/newcustomer/
&surname=[Surname to set for the new customer] 
 &firstname=[First Name to set for the new customer] 
 &email=[Email to set for the new customer] 
 &mobilephone=[Mobile Phone to set for the new customer] 
 &country=[Country to set for the new customer]
Add Customer to Oder 
 /jsonservice/v1/orderaddcustomer/
&orderid=[ID of order] 
 &customerid=[ID of customer]
Get Customer (by id) 
 /jsonservice/v1/customer/
&customerid=[ID of customer]
Get Customer (by order id) 
 /jsonservice/v1/ordercustomer/
&orderid=[ID of order]
Verify Customer : check if order have customer 
 /jsonservice/v1/orderhavecustomer/
&orderid=[ID of order]
Make a booking
Make a booking is : 
create an order : /jsonservice/v1/neworder/ 
create and add customer to the order : 
create customer : /jsonservice/v1/newcustomer/ 
add customer to the order : /jsonservice/v1/orderaddcustomer/ 
add item to the order : /jsonservice/v1/orderadditem/ 
complete order : /jsonservice/v1/completeorder/

Notes :
&parameter (in red) : mandatory field.
