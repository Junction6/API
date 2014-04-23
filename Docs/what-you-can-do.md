<table><tbody>
<tr>
<td class=""><p><strong>API Call</strong></p></td>
<td class=""><p><strong>Available Parameters</strong></p></td>
</tr>
<tr>
<td class=""><p><strong>Get Products</strong> <br class="atl-forced-newline">
/jsonservice/v1/products/</p></td>
<td class=""><p>&amp;p<em>roductid</em>=[ID of product] <strong>OR</strong> &amp;<em>productcode</em>=[Code of product] <br class="atl-forced-newline">
&amp;<em>limit</em>=[Integer] <br class="atl-forced-newline">
&amp;<em>fields</em>=[name of field1, name of field2, ...] <br class="atl-forced-newline">
&amp;<em>live</em>=[0 OR 1]</p></td>
</tr>
<tr>
<td class=""><p><strong>Create New Order</strong> : create an empty order. <br class="atl-forced-newline">
/jsonservice/v1/neworder/</p></td>
<td class=""><p>No parameters.</p></td>
</tr>
<tr>
<td class=""><p><strong>Get Order</strong> <br class="atl-forced-newline">
/jsonservice/v1/order/</p></td>
<td class=""><p>`&amp;orderid`=[ID of order]</p></td>
</tr>
<tr>
<td class=""><p><strong>Delete Order</strong> <br class="atl-forced-newline">
/jsonservice/v1/deleteorder/</p></td>
<td class=""><p><code>&amp;orderid</code>=[ID of order]</p></td>
</tr>
<tr>
<td class=""><p><strong>Clear Order</strong> : remove all items from order. <br class="atl-forced-newline">
/jsonservice/v1/clearorder/</p></td>
<td class=""><p><span style="color: rgb(220,35,0);">&amp;<em>orderid</em></span>=[ID of order]</p></td>
</tr>
<tr>
<td class=""><p><strong>Remove Item from Order</strong> <br class="atl-forced-newline">
/jsonservice/v1/orderdeleteitem/</p></td>
<td class=""><p><font color="red"><em>&amp;orderid</em></font>=[ID of order] <br class="atl-forced-newline">
<span style="color: rgb(220,35,0);">&amp;<em>orderitemid</em></span>=[ID of order item]</p></td>
</tr>
<tr>
<td class=""><p><strong>Get Availability</strong> <br class="atl-forced-newline">
/jsonservice/v1/availability/</p></td>
<td class=""><p><span style="color: rgb(220,35,0);">&amp;p<em>roductid</em></span>=[ID of product] <span style="color: rgb(220,35,0);"><strong>OR</strong> &amp;<em>productcode</em></span>=[Code of product] <br class="atl-forced-newline">
&amp;<em>date</em>=[date : YYYY-MM-DD] (today by default)</p></td>
</tr>
<tr>
<td class=""><p><strong>Add Item to Oder</strong> <br class="atl-forced-newline">
/jsonservice/v1/orderadditem/</p></td>
<td class=""><p><span style="color: rgb(220,35,0);">&amp;<em>orderid</em></span>=[ID of order] <br class="atl-forced-newline">
<span style="color: rgb(220,35,0);">&amp;p<em>roductvariation</em></span>=[ID of price variation] <br class="atl-forced-newline">
&amp;<em>quantity</em>=[Quantity of the item] (1 by default) <br class="atl-forced-newline">
&amp;<em>eventid</em>=[ID of event]</p></td>
</tr>
<tr>
<td class=""><p><strong>Complete Order</strong> <br class="atl-forced-newline">
/jsonservice/v1/completeorder/</p></td>
<td class=""><p><span style="color: rgb(220,35,0);">&amp;<em>orderid</em></span>=[ID of order]</p></td>
</tr>
<tr>
<td class=""><p><strong>Create New Customer</strong> <br class="atl-forced-newline">
/jsonservice/v1/newcustomer/</p></td>
<td class=""><p>&amp;<em>surname</em>=[Surname to set for the new customer] <br class="atl-forced-newline">
&amp;<em>firstname</em>=[First Name to set for the new customer] <br class="atl-forced-newline">
&amp;<em>email</em>=[Email to set for the new customer] <br class="atl-forced-newline">
&amp;<em>mobilephone</em>=[Mobile Phone to set for the new customer] <br class="atl-forced-newline">
&amp;<em>country</em>=[Country to set for the new customer]</p></td>
</tr>
<tr>
<td class=""><p><strong>Add Customer to Oder</strong> <br class="atl-forced-newline">
/jsonservice/v1/orderaddcustomer/</p></td>
<td class=""><p><span style="color: rgb(220,35,0);">&amp;<em>orderid</em></span>=[ID of order] <br class="atl-forced-newline">
<span style="color: rgb(220,35,0);">&amp;<em>customerid</em></span>=[ID of customer]</p></td>
</tr>
<tr>
<td class=""><p><strong>Get Customer</strong> (by id) <br class="atl-forced-newline">
/jsonservice/v1/customer/</p></td>
<td class=""><p><span style="color: rgb(220,35,0);">&amp;<em>customerid</em></span>=[ID of customer]</p></td>
</tr>
<tr>
<td class=""><p><strong>Get Customer</strong> (by order id) <br class="atl-forced-newline">
/jsonservice/v1/ordercustomer/</p></td>
<td class=""><p><span style="color: rgb(220,35,0);">&amp;<em>orderid</em></span>=[ID of order]</p></td>
</tr>
<tr>
<td class=""><p><strong>Verify Customer :</strong> check if order have customer <br class="atl-forced-newline">
/jsonservice/v1/orderhavecustomer/</p></td>
<td class=""><p><span style="color: rgb(220,35,0);">&amp;<em>orderid</em></span>=[ID of order]</p></td>
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
<code><strong>&amp;parameter</strong></code>'s displayed like this are mandatory.
