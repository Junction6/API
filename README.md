API V1
===

The J6 API and Documentation

top level functions
api.junction6travel.com/v1/
pass ?token &sessionID for first login
always pass ?sessionID after
Utils:
ping
getCurrencyList
postCurrency
getCurrency
topBooking
Reads:
getSuppliers
getProductsBySupplier
getProductsByTag
getProducts
Input Options:
Find and filter options:
/products/?find[tag.title][]=%tour%&find[tag.title][]=%route%&filter[supplier.name]=BenCo
Limit options:
/products/?limit=10&start=30
Field & connection options:
/products/?fields[]=Supplier&fields[]=ProductID&fields[]=Title
/product/123/?fields=ProductID,ExtraProducts Or:
/Products/?fields=ProductID,Title,Supplier,Tags
Connection Filter options (complex joins):
/Products/?fields=ProductID,Title,Supplier,Tags&Tags_find[]=123&Tags_fields=Title&Supplier_fields[]=SupplierID,Tags
Summary Fields (for lists):
ProductID
ProductCode
Title
SupplierName
BrandName
DetailsLink
Detail Fields (single product):
Summary Fields +
SupplierID
BrandID
Variations
Features
WhatToBring
Itinerary
RequiredCustomerFields
RequiredBookingFields
Optional Fields:
VoucherContent
VoucherContentFooter
SupplierCommission (Supplier or admin login)
AgentCommission (Agent or admin login)
Auto Connections: (return linked records):
Variations
Optional Connections: (return linked records):
Brand - Brand object
Supplier - Supplier Object
PickupLocations - Location set
ExtraProducts - Product Set
Tags - Condensed tag group set
getProduct
Alias of /product/xxx
Used when rest methods aren't supported (ie getProduct, postProduct, deleteProduct)
see Products section
getProductDetails
getProductSchedule
checkAvailability
getBookingState
Writes:
holdBooking(reserve item)
editBooking(change details) editCustomer(customer details)
processBooking(place order) - make payment
makeBooking (single request booking)
typical Input array:
{
  "Items": [{
      "ProductID": 123,
      "VariationID": 9876,
      "Quantity": 1,
      "PickupLocationID": 98,
      "EventID": 12938,
      "Comments": [{
        "Comment": "Customer note"
      }]
    },
    {
      "ProductID": 123,
      "Variation": [{
        "VariationID": 9876,
        "Quantity": 1
       }, 
       {
        "VariationID": 9876,
        "Quantity": 1
      }]

  }],
  "Customer": [{
    "FirstName": "James",
    "Surname": "Jones",
    "Email": "james.jones@mymail.com",
  }],
 "Payment": [{
    "Type": "AgentVoucher",
    "Value": "123.97",
    "Currency": "nzd",
  }]
}
Error Responses:
cancelBooking(whole or part)

