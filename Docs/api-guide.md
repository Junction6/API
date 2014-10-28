#GENERAL
Data Format : **JSON** (JavaScript Object Notation)

#SUMMARY
Methods can be accessed via url : [http://api.junction6travel.com]

Request methods via API : **BASE + METHOD + OPTIONS + TOKEN**

**BASE** : url for connection (for tests) : [http://api-beta.junction6travel.com] + /jsonservice/v1/

**METHOD** : api method desired, eg. 'products' (to get a list of live products)

**OPTIONS** : options to filter products, eg 'limit=10'

**TOKEN** : security token for current connection - mandatory for all api connections




#TOKENS

All requests must include the token parameter: 

> ?token=

**Note**: connection tokens for real clients can be requested.

**Demo Client**: 43e9457e334df268270a9d7b275d3700

**Testing Client**: 877f5fb686af0e5f5fcfb6d284fab3f9


#METHODS

All available methods are listed in the document file ["Available API Requests"](https://github.com/Junction6/API/blob/V1/Docs/available-requests.md).


#OPTIONS

Examples using the "products" method. Get all products: 

> /products/?token=xyz


## limit

Limit results to 500 first products (get all products could not work if lot of products): 

> /products/?token=xyz&limit=500


---


## fields

Get specified fields.  If the field is itself an Object it is possible to use dot notation to also specify fields within that Object.  Listed fields should be comma seperated:

> /products/?token=xyz&ProductID=1911&fields=ID,Title,Supplier.ID,Supplier.Name


---


## filter

Filter Results by Field: 

/products/?token=xyz&filter[SupplierID]=4321

Multiple filters can be used:

/products/?token=xyz&filter[ClassName]=LimitedAvailabilityDateAndTimeProduct&filter[ShowOnWhitelabel]=1


---



#GET AVAILABILITY (of the product)
You need to know the ID or the Code of the product you want to search availability for.
In the part "Options" of the URL you will need to include &ProductID= or &ProductCode=
If the product is not a limited availability product the response "true" will be sent.

```JSON
{
    "response": true
}
```

Example : 
> http://api.junction6travel.com/jsonservice/v1/availability/?token=2c9d47960b6a54be2e11c70007069b4c&ProductID=1234


# RETURN FORMAT

**On Success**
>	__JSON Object containing:__

>	"response"  - _Object_ -	Contains all return data.

#### On Failure
>	__JSON Object containing:__

>	"message"	- _String_ -	Reason for failure.

>	"status"	- _Integer_ -	HTTP status code.



#EXAMPLES
All products for Demo Client:

> http://api.junction6travel.com/jsonservice/v1/products/?token=43e9457e334df268270a9d7b275d3700


Get 50 products for Demo Client:

> http://api.junction6travel.com/jsonservice/v1/products/?token=43e9457e334df268270a9d7b275d3700&limit=50

Get all products for Demo Client but limit the Variations to the first 2 variations:

> http://api.junction6travel.com/jsonservice/v1/products/?token=43e9457e334df268270a9d7b275d3700&variations_limit=1,2

Get one Product by ID, only retrieve the Product Title and the Supplier ID:

> http://api.junction6travel.com/jsonservice/v1/products/?token=43e9457e334df268270a9d7b275d3700&productid=1234&fields=Title,Supplier.ID

Get Todays Events for a Limited Availability Product:

> http://api.junction6travel.com/jsonservice/v1/products/?token=43e9457e334df268270a9d7b275d3700&productid=1234&fields=Event.TodaysEvents

Get all Products by Supplier ID, return the ID and Title of the Product:

> http://api.junction6travel.com/jsonservice/v1/products/?token=43e9457e334df268270a9d7b275d3700&filter[SupplierID]=4321&fields=ID,Title


