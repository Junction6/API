<table><tbody>
<tr>
<td class=""><p><strong>API Call</strong></p></td>
<td class=""><p><strong>Available Parameters</strong></p></td>
</tr>
<tr>
<td class=""><p><strong>Get Products</strong> <br class="atl-forced-newline">
/jsonservice/v1/products/</p></td>
<td class=""><p><code>&amp;productid=[ID of product]</code> <strong>OR</strong> <code>&amp;productcode=[Code of product]</code> <br class="atl-forced-newline">
<code>&amp;<em>limit</em>=[Integer]</code> <br class="atl-forced-newline">
<code>&amp;<em>fields</em>=[name of field1, name of field2, ...]</code> <br class="atl-forced-newline">
<code>&amp;<em>live</em>=[0 OR 1]</code></p></td>
</tr>
<tr>
<td class=""><p><strong>Create New Order</strong> : create an empty order. <br class="atl-forced-newline">
/jsonservice/v1/neworder/</p></td>
<td class=""><p>No parameters.</p></td>
</tr>
<tr>
<td class=""><p><strong>Get Order</strong> <br class="atl-forced-newline">
/jsonservice/v1/order/</p></td>
<td class=""><p><code><strong>&amp;orderid=[ID of order]</code></strong></p></td>
</tr>
<tr>
<td class=""><p><strong>Delete Order</strong> <br class="atl-forced-newline">
/jsonservice/v1/deleteorder/</p></td>
<td class=""><p><code><strong>&amp;orderid=[ID of order]</strong></code></p></td>
</tr>
<tr>
<td class=""><p><strong>Clear Order</strong> : remove all items from order. <br class="atl-forced-newline">
/jsonservice/v1/clearorder/</p></td>
<td class=""><p><code><strong>&amp;orderid=[ID of order]</strong></code></p></td>
</tr>
<tr>
<td class=""><p><strong>Remove Item from Order</strong> <br class="atl-forced-newline">
/jsonservice/v1/orderdeleteitem/</p></td>
<td class=""><p><code><strong>&amp;orderid=[ID of order]</strong></code> <br class="atl-forced-newline">
<code><strong>&amp;orderitemid=[ID of order item]</strong></code></p></td>
</tr>
<tr>
<td class=""><p><strong>Get Availability</strong> <br class="atl-forced-newline">
/jsonservice/v1/availability/</p></td>
<td class=""><p><code><strong>&amp;productid=[ID of product]</strong></code> OR <code><strong>&amp;productcode=[Code of product]</strong></code> <br class="atl-forced-newline">
<code>&amp;<em>date</em>=[date : YYYY-MM-DD]</code> (today by default)</p></td>
</tr>
<tr>
<td class=""><p><strong>Add Item to Oder</strong> <br class="atl-forced-newline">
/jsonservice/v1/orderadditem/</p></td>
<td class=""><p><code><strong>&amp;orderid=[ID of order]</code></strong> <br class="atl-forced-newline">
<code><strong>&amp;productvariation=[ID of price variation]</code></strong> <br class="atl-forced-newline">
<code>&amp;<em>quantity=[Quantity of the item]</code> (1 by default) <br class="atl-forced-newline">
<code>&amp;<em>eventid=[ID of event]</code></p></td>
</tr>
<tr>
<td class=""><p><strong>Complete Order</strong> <br class="atl-forced-newline">
/jsonservice/v1/completeorder/</p></td>
<td class=""><p><code><strong>&amp;orderid=[ID of order]</code></strong></p></td>
</tr>
<tr>
<td class=""><p><strong>Create New Customer</strong> <br class="atl-forced-newline">
/jsonservice/v1/newcustomer/</p></td>
<td class=""><p><code>&amp;<em>surname</em>=[Surname to set for the new customer]</code> <br class="atl-forced-newline">
<code>&amp;<em>firstname</em>=[First Name to set for the new customer]</code> <br class="atl-forced-newline">
<code>&amp;<em>email</em>=[Email to set for the new customer]</code> <br class="atl-forced-newline">
<code>&amp;<em>mobilephone</em>=[Mobile Phone to set for the new customer]</code> <br class="atl-forced-newline">
<code>&amp;<em>country</em>=[Country to set for the new customer]</code></p></td>
</tr>
<tr>
<td class=""><p><strong>Add Customer to Oder</strong> <br class="atl-forced-newline">
/jsonservice/v1/orderaddcustomer/</p></td>
<td class=""><p><code><strong>&amp;orderid</code></strong>=[ID of order] <br class="atl-forced-newline">
<code><strong>&amp;customerid</code></strong>=[ID of customer]</p></td>
</tr>
<tr>
<td class=""><p><strong>Get Customer</strong> (by id) <br class="atl-forced-newline">
/jsonservice/v1/customer/</p></td>
<td class=""><p><code><strong>&amp;customerid</code></strong>=[ID of customer]</p></td>
</tr>
<tr>
<td class=""><p><strong>Get Customer</strong> (by order id) <br class="atl-forced-newline">
/jsonservice/v1/ordercustomer/</p></td>
<td class=""><p><code><strong>&amp;orderid</code></strong>=[ID of order]</p></td>
</tr>
<tr>
<td class=""><p><strong>Verify Customer :</strong> check if order have customer <br class="atl-forced-newline">
/jsonservice/v1/orderhavecustomer/</p></td>
<td class=""><p><code><strong>&amp;orderid</code></strong>=[ID of order]</p></td>
</tr>
<tr>
<td class=""><p><strong>Make a booking</strong></p></td>
<td class=""><p>Make a booking is : <br class="atl-forced-newline"></p>
<ul class="alternate">
	<li>create an order : /jsonservice/v1/neworder/ <br class="atl-forced-newline"></li>
	<li>create and add customer to the order : <br class="atl-forced-newline"></li>
	<li>create customer : /jsonservice/v1/newcustomer/ <br class="atl-forced-newline"></li>
	<li>add customer to the order : /jsonservice/v1/orderaddcustomer/ <br class="atl-forced-newline"></li>
	<li>add item to the order : /jsonservice/v1/orderadditem/ <br class="atl-forced-newline"></li>
	<li>complete order : /jsonservice/v1/completeorder/</li>
</ul>
</td>
</tr>
</tbody></table>

Notes :
<code><strong>&amp;parameter</strong></code>'s displayed in bold like this are mandatory.
