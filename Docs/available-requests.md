# API Doc v1

A description of Objects referenced here can be found in the [Appendix](https://github.com/Junction6/API/blob/V1/Docs/appendix.md).

## Utils (HTTP GET):

### neworder
**Required Parameters**

**_none_**

**Optional Parameters**

* **_customerid_** - Specify an existing customer id to attach to this new order.
* **_Customer_** - An array of Customer parameters to give the newly created Customer on this new order.  Reference the [Customer Object](https://github.com/Junction6/API/blob/V1/Docs/appendix.md#customerobject) for possible fields to set.  Cannot be used in conjunction with parameter **_customerid_**. To update an existing customer use **setcustomer**

**Response**

* **_OrderObject_**

---


### completeorder
**Required Parameters**

* **_OrderID_**

**Response**

* **_OrderObject_**

---


### deleteorder
**Required Parameters**

* **_OrderID_**

**Response**

* **_OrderObject_**

---


### clearorder
**Required Parameters**

* **_OrderID_**

**Response**

* **_OrderObject_**

---


### newcustomer
**Required Parameters**

**_none_**

**Response**

* **_CustomerObject_**

---


### setcustomer
**Required Parameters**

**_customerid_** _String_ - ID of the existing Customer to edit.

**Optional Parameters**

Any fields found in the [Customer Object](https://github.com/Junction6/API/blob/V1/Docs/appendix.md#customerobject).

**Response**

* **_CustomerObject_**

---
    


### orderadditem
**Required Parameters**

* **_orderid_** _String_ - ID of the order to add item to.

* **_productvariation_** OR **_productid_**  - In most cases the product variation is required but some products may be purchased using only the Product ID (Gift Voucher)

**Required Parameters for Limited Availabilty Items**

* **_eventid_** _String_ - ID of the event to book.

**Optional Parameters For Gift Voucher Items**

* **_firstname_** _String_ - Required to create the recipient, cannot be omitted if surname and/or email are included

* **_surname_** _String_ - Optional with firstname

* **_email_** _String_ - - Optional with firstname

* **_giftmessage_** _String_  - Optional message from the purchaser to the recipient.

**Response**

* **"Order"**   - _OrderObject_ -   The complete OrderObject with extra embedded properties "NewOrderItem" - OrderItemObject and "NewOrderItemID".



---


### orderdeleteitem
**Required Parameters**

* **_orderid_**

* **_itemid_**

**Response**

* **"Order"**   - _OrderObject_ -   The order specified in OrderID.


---


### orderaddpayment
**Required Parameters**

* **_OrderID_**  

* **_Amount_**  

**Response**

* **"Success"** - _Boolean_ -      Success status of the payment.

* **"Order"**   - _OrderObject_ -   The order specified in OrderID.


---


## Utils (HTTP POST):

### authenticateCustomer
**Required Parameters**

**_username_** - _String_ Encrypted username

**_password_** - _String_ Encrypted password

**Response**

* **_CustomerObject_** On success or Error Message "Invalid login attempt" on failure with status code 403 Forbidden.

**Notes**

This method is only available through HTTP POST. Both username and password must be encryted with the agreed upon cipher method, mode, key and IV.


---





## Reads (HTTP GET):

### getorder
**Required Parameters**

* **_OrderID_**  

**Response**

* **_OrderObject_**

---


### ordersbydatecreated
**Required Parameters**

* **_startdate_** - Begining of date range to search, format: YYYY-MM-DD (time will be set to 00:00:00)
* **_enddate_** - End of date range to search, format: YYYY-MM-DD (time will be set to 23:59:59)

**Response**

* **_Array_** - _Array_ of OrderIDs

---


### getcustomer
**Required Parameters**

* **_CustomerID_**

**Response**

* **_CustomerObject_**

---


### customerorders
**Required Parameters**

* **_customerid_**

**Response**

* **_Array_** - Array of OrderIDs

---



### products
**Required Parameters**

**_none_**  

**Optional Parameters**

* **_live_**

* **_productcode_**

* **_productclassname_**

**Response**

* **_Array of ProductObjects_**

---



### getGiftVoucher
**Required Parameters**

**_vouchercode_**

**Response**

* **_GiftVoucherItemObject_**


---


### products
**Required Parameters**

*none*

**Optional Parameters**

* **_productid_**  - Can be a single ID or a comma seperated list of IDs to return an array of ProductObjects
* **_productcode_**
* **_live_**

**Response**

* **_ProductObject_** or _Array of ProductObjects_


_Note: supplying no parameters to this method will produce a response containing an array of **ALL ProductObjects**
---


### availability
**Required Parameters**

* **_productid_** OR **_productcode_**

**Optional Parameters**

* **_date_** OR ( **_startdate_** AND **_enddate_** ) - All of these parameters are Strings in the format: "Y-m-d".  If **_date_** is given events on that day are returned. If **_date_** is excluded and **_startdate_** and **_enddate_** are given then we have an inclusive date range to search. If none of these parameters are supplied date defaults to todays date.

**Response**

* **"items"** - _Array of EventObjects_ -


---


### getPickupPoints
**Required Parameters**

**_none_**

**Response**

* **"PickupPoints"** - _Array of PickupPointObjects_ -


---


