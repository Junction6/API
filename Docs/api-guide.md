#GENERAL
Data Format : **JSON** (JavaScript Object Notation)

#SUMMARY
Products can be accessed via url : [http://api.junction6travel.com]

Request products via API : **BASE + OPTIONS + TOKEN**

**BASE** : url for connexion (for tests) : [http://api.junction6travel.com] + /jsonservice/v1/

**OPTIONS** : options to filter products 

**TOKEN** : security token for current connexion


#OPTIONS (search products)
Examples:

Get all products: /products/

Limit results to 500 first products (get all products could not work if lot of products): /products/&limit=500

Get product by id: /&ProductID=1911

Get specified fields: /&fields=ProductID,Title,...


#GET AVAILABILITY (of the product)
You need to know the ID or the Code of the product you want to search availability for.
In the part "Options" of the URL you will need to include &ProductID= or &ProductCode=
If the product do not require availabilities, the response "true" will be sent.

```JSON
{
    response: true
}
```
Example : http://api.junction6travel.com/jsonservice/v1/availability/&ProductID=4893?token=2c9d47960b6a54be2e11c70007069b4c


TOKENS (by Client)
**Note**: connexion tokens for real clients can be requested.

**Demo Client**: 43e9457e334df268270a9d7b275d3700

**Testing Client**: 877f5fb686af0e5f5fcfb6d284fab3f9


#EXAMPLES
All products for Demo Client:
http://api.junction6travel.com/jsonservice/v1/products/?token=43e9457e334df268270a9d7b275d3700

Get 50 products for Outback:
http://api.junction6travel.com/jsonservice/v1/products/&limit=50?token=47a34de20017519e0a6084bbc9a967f9
