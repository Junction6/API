API Intro
===

Get current or new Order object

####Connect
```php
$APIKey = 'OBC-1234';
$secretToken = 'SdF$89w3tr#h3twfo934%893eHhf55^&';

try {
    J6API::Authenticate($APIKey, $secretToken);
} catch (Exception $e) {
    echo 'J6 API Connection Issue: ',  $e->getMessage(), "\n";
} 
```

####Find Order
Takes either a numberic id or an array contain in search data
```php
$order = j6Order::find($id)
// Will return a single record

```

```php
$data = array('FirstName' => 'John', 'Surname' => 'Smith%');
$order = j6Order::find($data);
// Will return a single record or an array

if(is_array($order)) {
    //Display list or orders
} else {
    //Do something with result
}

```



```php
$data = $_REQUEST;

if(!isset($data['productDetails']) || !isset($data['customerDetails']) || isset($data['paymentDetails'])) {
    echo 'Not enough data was supplied to make this booking';
    return;
}

$order = J6API::Order();
$order->addOrderItem($data['productDetails']);
$order->addCustomer($data['customerDetails']);
$order->addPayment($data['paymentDetails']);

try {
    $orderRecord = $order->placeOrder();
} catch (Exception $e) {
    echo $e->getMessage();
    return;
}

echo 'Your order was successful. Your Order Number is #' . $orderRecord->ID;

```

Or

```php
$order = new J6Order();
$order->addOrderItem($data['productDetails']);

$customer = new J6Customer($customerData);
$customerID = $customer->ID;
echo 'Your Customer Number is #'. $customerID;

$order->addCustomer($customer);
```
