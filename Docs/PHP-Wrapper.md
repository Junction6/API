API Intro
===

Get current or new Order object

$APIKey = ‘OBC-1234’;
$secretToken = ‘SdF$89w3tr#h3twfo934%893eHhf55^&’;

try {
    J6API::Authenticate($APIKey, $secretToken);
} catch (Exception $e) {
    echo ‘J6 API Connection Issue: ',  $e->getMessage(), "\n";
} 



```php
$data  = $_REQUEST;

if(!isset($data[‘productDetails’]) || !isset($data[‘customerDetails’]) || isset($data[‘paymentDetails’])) {
    echo ’Not enough data was supplied to make this booking’;
    return;
}

$order = J6API::Order();
$order->addOrderItem($data[‘productDetails’]);
$order->addCustomer($data[‘customerDetails’]);
$order->addPayment($data[‘paymentDetails’]);

try {
    $orderRecord = $order->placeOrder();
} catch (Exception $e) {
    echo $e->getMessage();
    return;
}

echo ‘Your order was successful. Your Order Number is #’ . $orderRecord.ID;

```

Or

```php
$order = new J6Order();
$order->addOrderItem($data[‘productDetails’]);

$customer = new J6Customer($customerData);
$customerID = $customer->ID;
echo ‘Your Customer Number is #’. $customerID;

$order->addCustomer($customer);
```