# API Appendix

## API Object Format Appendix

### OrderObject
* **"ExternalOrderID"**	- _Integer_ -	Reference ID for this Order.
* **"Items"**     		- _Array of OrderItemObjects_ -	Items belonging to this order.
* **"Customer"**  		- _CustomerObject_ -	Details of the customer attached to this order.
* **"Status"**    		- _String_ -	The current status of this order.

---


### OrderItemObject
__An OrderItemObject will include the following fields at minimum and may include more depending on the type of item__

* **"ID"**	- _Integer_ -	Reference ID for this Order Item.
* **"ItemStatus"**     	- _String_ -	Order Item status, one of 'Active', 'Cancelled', 'Inactive'.
* **"OrderID"**  		- _Integer_ -	Reference ID of the Order that this orderitem belongs to.
* **"UnitPrice"**    	- _Float_ -		Price the item was sold at, per unit.
* **"FeeOrDiscount"**   - _String_ -	One of 'Fee','Discount'.
* **"FeeOrDiscountAmount"**	- _Float_ -	Value of the Fee or Discount, if any.
* **"Quantity"**    	- _Integer_ -	Number of units purchased.
* **"RedeemableDate"**	- _String_ -	Date String, date that this item became redeemable.
* **"Supplier"**    	- _SupplierObject_ -	Details of the Supplier, if any.


__Below are types of extended ProductObjects by classname with their extra fields__

### EventOrderItemObject / LimitedAvailabilityDateProductOrderItemObject

* **"CustomerSequenceNumber"**	- _String_ -	Customers sequence number (for the day of this Event)
* **"Event"**	- _EventObject_ -	Detail of the Event this item is attched to.

---


### GiftVoucherOrderItemObject

* **"VoucherTitle"**	- _String_ -	Name of the Gift Voucher.
* **"GiftVoucherCode"**	- _String_ -	Unique Code.
* **"Customer"**	- _CustomerObject_ -	The customer who originally bought the Gift Voucher.
* **"AssignedToCustomer"**	- _CustomerObject_ -	The customer, if any, who the Gift Voucher was assigned to.
* **"ExpiryDate"**	- _String_ -	Date string.
* **"AmountRemaining"**	- _Float_ -		Current value.
* **"Status"**	- _String_ -	Gift Voucher status, one of 'Active', 'Expired', 'Redeemed', 'Cancelled'.

---


### CustomerObject
* **"ID"**		- _Integer_ -	Reference ID for this Customer.
* **"FirstName"**	- _String_ -	Customer first name.
* **"Surname"**	- _String_ -	Customer surname.
* **"Country"** 	- _String_ -	Country Acronym.
* **"Email"**   	- _String_ -	Email address.
* **"Mobile Phone"**	- _String_ -	Customer mobile phone number.

---


### ProductObject
__A ProductObject will include the following fields at minimum and may include more depending on the type of product__

* **"ID"** 'ID'	Reference ID for this Product.
* **"Title"** - _String_ -
* **"Recommended"** - _Boolean_ -
* **"HotDeal"** - _Boolean_ -
* **"Affiliate"** - _Boolean_ -
* **"AffiliatelURL"** - _String_
* **"AllowAgencyPurchase"** - _Boolean_ -
* **"ShowOnWhitelabel"** - _Boolean_ -
* **"AgencyCommissionType"** - _String_	One of 'None', 'Inherit', 'Percentage', 'Fixed'
* **"AgencyCommission"** - _Float_ Represents a percentage of price or fixed value
* **"Price"** - _Float_ 
* **"Weight"** - _Float_ 
* **"Model"** 'Model',
* **"FeaturedProduct"** - _Boolean_ -
* **"AllowPurchase"** - _Boolean_ -
* **"InternalItemID"** - _String_ - May be SKU
* **"Features"** - _String_ HTML text
* **"WhatToBring"** - _String_ HTML text
* **"Itinerary"** - _String_ HTML text
* **"WhitelabelContentFooter"** - _String_ HTML text
* **"Content"** - _String_ HTML text
* **"BookingInfo"** - _String_ HTML text
* **"Supplier"** - _SupplierObject_ -
* **"Variations"** - _Array of VariationObjects_ -
* **"Location"** -_LocationObject_ -
* **"ProductPickupLocations"** -_Array of ProductPickupLocationObjects_ -
* **"SpecialPrices"** -_Array of SpecialPriceObjects_ -
* **"ExtraProducts"** -_Array of ExtraProductObjects_ -


__Below are types of extended ProductObjects by classname with their extra fields__

### GiftVoucherProduct

* **"Expires"**	- _Boolean_ -
* **"ExpiryType"**	- _String_ -	One of 'Offset', 'SetDate'
* **"ExpiryOffsetMonths"**	- _Integer_ -	Months from purchase date the voucher will expire
* **"FixedExpiryDate"**	- _String_ -	Date string, will be set if this type of Voucher has a fixed expiry
* **"ExpiryIsEditable"**	- _Boolean_ -
* **"IsTransferable"**	- _Boolean_ -	May be used by another Customer.
* **"FixedPrice"**	- _Boolean_ -	Specifies if the price is editable at time of sale.
* **"PartialRedeem"**	- _Boolean_ -	Can the voucher be redeemed in parts or must be redeemed in full on first usage.
* **"CodeIsEditable"**	- _Boolean_ -	Can the voucher code be edited - subject to unique check
* **"AllowMessage"**	- _Boolean_ -	
* **"EmailSubject"**	- _String_ -	


### LimitedAvailabilityDateProduct / LimitedAvailabilityDateAndTimeProduct

* **"canFreesell"**	- _Boolean_ -	May be sold without making a date/time booking.
* **"SurchargePax"**	- _Integer_ -	Minimum number of bookings required to avoid a surcharge.
* **"SurchargePerPax"**	- _Float_ -		Surcharge incurred per passenger if minimum number of bookings not met.
* **"TodaysEvents"**	- _Array of EventObjects_ -
* **"Next10Events"**	- _Array of EventObjects_ -


### LimitedAvailabilityByPriceProduct
* **"RedeemableDate"**	- _String_ -
* **"RRP"**				- _Float_ -
* **"DailyAvailability"**	- _Integer_ -


---


### VariationObject
* **"ID"**		- _Integer_ -	Reference ID for this Product Variation.
* **"InternalItemID"**		- _String_ -	May be referencing SKU.
* **"Price"**		- _Float_ -		Price of the PRoduct Variation.
* **"Name"**		- _String_ -	Name of the Product Variation.
* **"LocalFeeTitle**		- _String_ -
* **"LocalFee**		- _Float_ -
* **"LocalFeeAddedToOrder**		- _Boolean_ -
* **"StartDate**		- _String_ -	Date String, start of validity period, blank if always valid.
* **"EndDate**		- _String_ -	Date String, end of validity period, blank if always valid.
* **"Description**		- _String_ -	Description text.

---


### EventObject

* **"ID"**		- _Integer_ -	Reference ID for this Event.
* **"Date"**		- _String_ -	Date String, date of the Event.
* **"Start"**		- _String_ -	Start time of the Event.
* **"End"**		- _String_ -	End time of the Event.
* **"Quantity"**		- _String_ -	Total quantity, before any bookings.
* **"Remaining"**		- _String_ -	Bookable quantity remaining.
* **"CanBook"**		- _Boolean_ -	Is the Event bookable (could be in the past).
* **"Unlimited"**	- _Boolean_ -	Unlimited availability.
* **"Description"**		- _String_ -	Event description.
* **"ManifestStatus"**		- _String_ -	Current manifest status, one of 'Unconfirmed', 'Open', 'Locked','Open'.
* **"Time"**		- _String_ -	Start and end time.


---


### SpecialPriceObject
* **"Title"**		- _String_ -	Title of the special price.
* **"Price"**		- _Float_ -
* **"StartDate"**	- _String_ -
* **"EndDate"**		- _String_ -	Date String, start of validity period.
* **"Active"**		- _String_ -	Date String, end of validity period.

---


### GiftVoucherItemObject
* **"ID"**
* **"Title"**		- _String_ -	Title of the Gift Voucher Product.
* **"UnitPrice"**		- _Float_ -	Original value of the Gift Voucher.
* **"Quantity"**		- _Integer_ -	Number of vouchers.
* **"Customer"**		- _CustomerObject_ -	The purchasing Customer.
* **"AssignedToCustomer"**		- _CustomerObject_ -	The Customer that this Gift Voucher has been assigned to or null if not assigned.
* **"GiftVoucherCode"**		- _String_ -	The unique code for this Gift Voucher.
* **"AmountRemaining"**		- _Float_ -		Usable monetary amount remaining on this Gift Voucher.
* **"Status"**		- _String_ -	One of 'Active', 'Expired', 'Redeemed', 'Cancelled'
* **"ExpiryDate"**		- _String_ -	Date String, expiry date.

### SupplierObject
* **"ID"**		- _Integer_ -	Reference ID for this Supplier.
* **"Internal"**	- _Boolean_ -	Is an internal supplier.
* **"Name"**	- _String_ -	
* **"Address"**	- _String_ -	
* **"Suburb"**	- _String_ -	
* **"City"**	- _String_ -	
* **"PostCode"**	- _String_ -	
* **"State"**	- _String_ -	
* **"Country"**	- _String_ -	
* **"CommissionType"**	- _String_ -	One of 'Inherit', 'None', 'Percentage', 'Fixed'
* **"Commission"**	- _Float_ -		Represents a percentage of product sold price or fixed value

---


### LocationObject
* **"ID"**		- _Integer_ -	Reference ID for this Location.
* **"Title"**		- _String_ -	Title of this Location.
* **"ShortCode"**		- _String_ -
* **"isAHub"**	- _Boolean_ -
* **"isInRoute"**	- _Boolean_ -

---

