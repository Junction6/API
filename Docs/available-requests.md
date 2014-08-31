# API Doc v1

A description of Objects referenced here can be found in the [Appendix](https://github.com/Junction6/API/blob/V1/Docs/appendix.md).

## Utils:

### neworder
**Required Parameters**

**_none_**

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
    


### orderadditem
**Required Parameters**

* **_orderid_**

* **_productvariation_** OR **_productid_**  - In most cases the product variation is required but some products may be purchased using only the Product ID (Gift Voucher)


**Response**

* **"Item"** - _Boolean_ -      Success status of the payment.

* **"Order"**   - _OrderObject_ -   The order specified in OrderID.


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






## Reads:

### getorder
**Required Parameters**

* **_OrderID_**  

**Response**

* **_OrderObject_**

---


### getcustomer
**Required Parameters**

* **_CustomerID_**  

**Response**

* **_CustomerObject_**

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

* **_productid_**
* **_productcode_**
* **_live_**

**Response**

* **_ProductObject_**


---


### availability
**Required Parameters**

* **_productid_** OR **_productcode_**

**Optional Parameters**

* **_date_** - Date String in format: "Y-m-d",  Defaults to todays date.

**Response**

* **"items"** - _Array of EventObjects_ -


---

