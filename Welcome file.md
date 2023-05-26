---


---

<h1 id="dms-intergation">DMS intergation</h1>
<h2 id="welcome">Welcome</h2>
<p>This is the place to learn about bskt’s merchant API, View API Documentation and to get help using the Merchant Portal.</p>
<h3 id="merchant-playground">Merchant Playground</h3>
<p><a href="https://merchant.stage.bsktpay.co/">View Here →</a></p>
<h3 id="merchant-open-ai-api-specification">Merchant Open AI API Specification</h3>
<p><a href="https://stage-merchant.api.bsktpay.co/v3/api-docs">View Here →</a></p>
<p><img src="https://drive.google.com/open?id=1ioaAA9cUC3Xo_D4Im4NIdz_gy7ndpGi5&amp;authuser=device@bskt.co&amp;usp=drive_fs" alt="enter image description here"></p>
<h2 id="getting-started">Getting started</h2>
<h3 id="authenication">Authenication</h3>
<p>Contact our Business Manager for <code>client_id</code> and <code>client_secret</code> credentials</p>
<h4 id="getting-an-access-token-for-your-api">Getting an access token for your API</h4>
<p>First, execute a client credentials exchange to get an  <code>access token</code>  for  API.</p>
<pre><code>curl --request POST \ --url https://bsktpay-stage.eu.auth0.com/oauth/token \ --header 'content-type: application/json' \ --data '{"client_id":"aaa","client_secret":"aaakQv","audience":"https://api.stage.bsktpay.co","grant_type":"client_credentials"}'
</code></pre>
<h4 id="response">Response</h4>
<pre><code>{ "access_token": "eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCIsImtpZCI6InVFMHVNMXNGQkt3OXhXQzZ5WFM0MSJ9.eyJpc3MiOiJodHRwczovL2Jza3RwYXktc3RhZ2UuZXUuYXV0aDAuY29tLyIsInN1YiI6ImxmU0pEQ1VSVUg3TVlkQ0o3NVRBQmZtWHVWS0lPdExwQGNsaWVudHMiLCJhdWQiOiJodHRwczovL2FwaS5zdGFnZS5ic2t0cGF5LmNvIiwiaWF0IjoxNjg0NDc4NDUyLCJleHAiOjE2ODQ1NjQ4NTIsImF6cCI6ImxmU0pEQ1VSVUg3TVlkQ0o3NVRBQmZtWHVWS0lPdExwIiwiZ3R5IjoiY2xpZW50LWNyZWRlbnRpYWxzIiwicGVybWlzc2lvbnMiOltdfQ.a51IfzXwbxWuOc6y_8l3pz0OJWdWLAbX5bqsi1QYgU1j2dE3SRwxIN44h-q1UYTTD6zuK7XODLFWWP492PYkePiH1Kz3Rc-to27TBz3KsabQADak5EvPo_T1Y9b_XVdDwZ6R_r4EijNQhbU947YYmMzILr1e-UQIq59fpGNDzAhkwq9ygd-MAeOflsx6ZRI6k4pd7erG6kywlZZnH67qxp7uuV90PMPVHX3ggwnYW-8tEwovakWxWhFJveHtRxVJn0Zg8tCGd3OesxHYQdJyO3Cbglelgy5OjCeQdEoNVqeO78rsF7UoMrV8W_N2w43VZSI3F7NXw_dda1Byu1EzmQ", "token_type": "Bearer" }
</code></pre>
<h4 id="thats-it">That’s it!</h4>
<p>Second, now that the application has an  <code>access_token</code>, it is now able to make authorized calls to the API.</p>
<h4 id="sending-the-token-api">Sending the token API</h4>
<p>You can use this  <code>bearer token</code>  with an  <code>Authorization Header</code>  in your request to obtain authorized access to your API.</p>
<pre><code>curl --request GET \ --url https://stage-merchant.api.bsktpay.co \ --header 'authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCIsImtpZCI6InVFMHVNMXNGQkt3OXhXQzZ5WFM0MSJ9.eyJpc3MiOiJodHRwczovL2Jza3RwYXktc3RhZ2UuZXUuYXV0aDAuY29tLyIsInN1YiI6ImxmU0pEQ1VSVUg3TVlkQ0o3NVRBQmZtWHVWS0lPdExwQGNsaWVudHMiLCJhdWQiOiJodHRwczovL2FwaS5zdGFnZS5ic2t0cGF5LmNvIiwiaWF0IjoxNjg0NDc4NDUyLCJleHAiOjE2ODQ1NjQ4NTIsImF6cCI6ImxmU0pEQ1VSVUg3TVlkQ0o3NVRBQmZtWHVWS0lPdExwIiwiZ3R5IjoiY2xpZW50LWNyZWRlbnRpYWxzIiwicGVybWlzc2lvbnMiOltdfQ.a51IfzXwbxWuOc6y_8l3pz0OJWdWLAbX5bqsi1QYgU1j2dE3SRwxIN44h-q1UYTTD6zuK7XODLFWWP492PYkePiH1Kz3Rc-to27TBz3KsabQADak5EvPo_T1Y9b_XVdDwZ6R_r4EijNQhbU947YYmMzILr1e-UQIq59fpGNDzAhkwq9ygd-MAeOflsx6ZRI6k4pd7erG6kywlZZnH67qxp7uuV90PMPVHX3ggwnYW-8tEwovakWxWhFJveHtRxVJn0Zg8tCGd3OesxHYQdJyO3Cbglelgy5OjCeQdEoNVqeO78rsF7UoMrV8W_N2w43VZSI3F7NXw_dda1Byu1EzmQ'
</code></pre>
<h2 id="schemas">Schemas</h2>
<p><strong>Product</strong></p>
<pre><code>id				integer($int64)
name			string
description		string
slug			string
approvedAt		string($date-time)
category*		Category{
					id integer($int64)
				}
productType*	ProductType{
			    	id integer($int64}
		    	}
sizeDescription	string
ageRestriction	boolean

stockControl	string Enum:  
				[  none, multiPurchase, purchaseOnce  ]
inStock			boolean
tax*			Tax{	
				    id integer($int64)
				}
unitPrice*		integer($int64)
</code></pre>
<p>*required</p>
<p><strong>Tax</strong></p>
<pre><code>id				integer($int64)
type*			string Enum:  
				[  none, multiPurchase, purchaseOnce  ]
rate*	  		integer($int32)
inclusive		boolean
country			Country{	
				    id integer($int64)
				}
description		string
</code></pre>
<h2 id="product">Product</h2>
<p><strong>Create a new product</strong></p>
<p>To create a new product, send a POST request to the <code>/products</code> endpoint. In the request body, provide the necessary information such as the <code>name</code>, <code>description</code>, <code>price</code>, and any additional required attributes for the product. The API will process the request and respond with the newly created product details.</p>
<pre class=" language-shell"><code class="prism  language-shell">curl -X POST -H "Content-Type: application/json" -d '{
  "name": "New Product",
  "description": "This is a new product.",
  "price": 19.99
  // Include any additional required attributes for the product
}' "https://stage-merchant.api.bsktpay.co/products"
</code></pre>
<p><strong>Get product details</strong></p>
<p>To retrieve the details of a specific product, make a GET request to the <code>/products/{productId}</code> endpoint. Replace <code>{productId}</code> with the actual ID of the product you want to retrieve. The response will contain information about the product, such as its name, description, price, and other relevant details.</p>
<pre class=" language-shell"><code class="prism  language-shell">curl -X GET "https://stage-merchant.api.bsktpay.co/products/{productId}"
</code></pre>
<p><strong>Update a product</strong></p>
<p>To update the information of a product, send a PUT request to the <code>/products/{productId}</code> endpoint, replacing <code>{productId}</code> with the actual ID of the product you want to update. In the request body, provide the updated values for the <code>name</code>, <code>description</code>, <code>price</code>, and any additional attributes you want to modify. The API will update the product accordingly and respond with the updated product details.</p>
<pre class=" language-shell"><code class="prism  language-shell">curl -X PUT -H "Content-Type: application/json" -d '{
  "name": "Updated Product Name",
  "description": "This is an updated product description.",
  "price": 24.99
  // Include any additional attributes to update
}' "https://stage-merchant.api.bsktpay.co/products/{productId}"
</code></pre>
<p><strong>Delete a product</strong></p>
<p>To delete a product, send a DELETE request to the <code>/products/{productId}</code> endpoint, replacing <code>{productId}</code> with the actual ID of the product you want to delete. The API will process the deletion request, and upon successful deletion, the product will no longer be available.</p>
<pre class=" language-shell"><code class="prism  language-shell">curl -X DELETE "https://stage-merchant.api.bsktpay.co/products/{productId}"
</code></pre>
<p><strong>Upload product image</strong></p>
<p>To upload an image for a specific product, send a GET request to the <code>/product/image/{productId}/generateUrl</code> endpoint, replacing <code>{productId}</code> with the actual ID of the product to retrieve a placeholder url.</p>
<p>Then send a POST to <code>/media/public/upload</code> to retrieve a presigned url</p>
<p>Use this url to upload the image to our secure environment. Set the request header <code>Content-Type</code> to <code>multipart/form-data</code> and include the image file using the <code>-F</code> flag, specifying the file path. The API will process the request and associate the uploaded image with the product.</p>
<p><strong>Get product image details</strong></p>
<p>To retrieve the details of a specific product image, make a GET request to the <code>/products/{productId}/images/{imageId}</code> endpoint. Replace <code>{productId}</code> with the actual ID of the product and <code>{imageId}</code> with the ID of the image you want to retrieve. The API will respond with information about the image, such as its URL, size, and other relevant details.</p>
<pre class=" language-shell"><code class="prism  language-shell">curl -X GET "https://stage-merchant.api.bsktpay.co/products/{productId}/images/{imageId}"
</code></pre>
<p><strong>Update product image details:</strong></p>
<p>To update the details of a specific product image, send a PUT request to the <code>/products/{productId}/images/{imageId}</code> endpoint, replacing <code>{productId}</code> with the actual ID of the product and <code>{imageId}</code> with the ID of the image you want to update. Set the request header <code>Content-Type</code> to <code>application/json</code> and provide the updated values in the request body. You can include attributes like <code>name</code>, <code>description</code>, and any additional attributes specified in the API schema definitions. The API will update the image details accordingly.</p>
<pre class=" language-shell"><code class="prism  language-shell">curl -X PUT -H "Content-Type: application/json" -d '{
  "name": "New Image Name",
  "description": "Updated image description"
  // Include any additional attributes to update
}' "https://stage-merchant.api.bsktpay.co/products/{productId}/images/{imageId}"
</code></pre>
<p><strong>Delete a product image</strong><br>
To delete a specific product image, send a DELETE request to the <code>/products/{productId}/images/{imageId}</code> endpoint, replacing <code>{productId}</code> with the actual ID of the product and <code>{imageId}</code> with the ID of the image you want to delete. The API will process the deletion request, and upon successful deletion, the image will no longer be associated with the product.</p>
<pre class=" language-shell"><code class="prism  language-shell">curl -X DELETE "https://stage-merchant.api.bsktpay.co/products/{productId}/images/{imageId}"
</code></pre>
<p><strong>Get QR code details:</strong><br>
To retrieve the details of a specific QR code that links to a product, make a GET request to the <code>/products/qr/{productId}</code> endpoint, replacing <code>{productId}</code> with the actual ID of the Product code you want to retrieve. The API will respond with information about the QR code, such as its URL, associated product, and other relevant details.</p>
<pre class=" language-shell"><code class="prism  language-shell">curl -X GET "https://stage-merchant.api.bsktpay.co/products/qr/{productId}"
</code></pre>
<h2 id="customer">Customer</h2>
<p>Getting started with customers are simple, here are some of the basic operations.</p>
<p><strong>Create a new customer</strong></p>
<p>To create a new customer, send a POST request to the <code>/customers</code> endpoint. In the request body, provide the necessary information such as the <code>name</code>, <code>email</code>, <code>address</code>, and any additional required attributes for the customer. The API will process the request and respond with the newly created customer details.</p>
<pre class=" language-shell"><code class="prism  language-shell">curl -X POST -H "Content-Type: application/json" -d '{
  "userDetail": {
      "id": 0,
      "title": "string",
      "firstName": "string",
      "surname": "string",
      "middleName": "string",
      "maidenName": "string",
      "emailAddress": "johndoe@example.com",
      "zoneId : "europe/london" 	    
       }
   // Include any additional required attributes for the customer
}' "https://stage-merchant.api.bsktpay.co/customers"
</code></pre>
<p><strong>Get customer details</strong><br>
To retrieve the details of a specific customer, make a GET request to the <code>/customers/{customerId}</code> endpoint. Replace <code>{customerId}</code> with the actual ID of the customer you want to retrieve. The response will contain information about the customer, such as their name, email, address, and other relevant details.</p>
<pre class=" language-shell"><code class="prism  language-shell">curl -X GET "https://stage-merchant.api.bsktpay.co/customers/{customerId}"
</code></pre>
<p><strong>Update customer details</strong><br>
To update the information of a customer, send a PUT request to the <code>/customers/{customerId}</code> endpoint, replacing <code>{customerId}</code> with the actual ID of the customer you want to update. In the request body, provide the updated values for the <code>name</code>, <code>email</code>, <code>address</code>, and any additional attributes you want to modify. The API will update the customer accordingly and respond with the updated customer details.</p>
<pre class=" language-shell"><code class="prism  language-shell">curl -X PUT -H "Content-Type: application/json" -d '{
    "userDetail": {
      "id": 0,
      "title": "string",
      "firstName": "string",
      "surname": "string",
      "middleName": "string",
      "maidenName": "string",
      "emailAddress": "johndoe@example.com",
      "zoneId : "europe/london" 	    
      }
  // Include any additional attributes to update
}' "https://stage-merchant.api.bsktpay.co/customers/{customerId}"
</code></pre>
<h2 id="customer-address">Customer Address</h2>
<p><strong>Create a new address</strong></p>
<p>To create a new address, send a POST request to the <code>/customers/{customerId}/addresses</code> endpoint. Set the request header <code>Content-Type</code> to <code>application/json</code> and provide the necessary information in the request body. The required attributes typically include <code>street</code>, <code>city</code>, <code>postalCode</code>, and any additional attributes specified in the API schema definitions. The API will process the request and return the details of the newly created address.</p>
<pre class=" language-shell"><code class="prism  language-shell">curl -X POST -H "Content-Type: application/json" -d '{
  "street": "123 Main St",
  "city": "Anytown",
  "postalCode": "12345",
  // Include any additional required attributes for the address
}' "/customers/{customerId}/addresses"
</code></pre>
<p><strong>Get address details</strong></p>
<p>To retrieve the details of a specific address, make a GET request to the <code>/customers/{customerId}/addresses</code> endpoint, replacing <code>{addressId}</code> with the actual ID of the address you want to retrieve. The API will respond with information about the address, such as street, city, postal code, and other relevant details- cURL Command:</p>
<pre class=" language-shell"><code class="prism  language-shell">curl -X GET "https://stage-merchant.api.bsktpay.co/customers/{customerId}/addresses"
</code></pre>
<p><strong>Update address details</strong></p>
<p>To update the information of an address, send a PUT request to the <code>/customers/{customerId}/addresses</code> endpoint, replacing <code>{addressId}</code> with the actual ID of the address you want to update. Set the request header <code>Content-Type</code> to <code>application/json</code> and provide the updated values in the request body. Typically, you’ll include attributes like <code>street</code>, <code>city</code>, <code>postalCode</code>, and any additional attributes specified in the API schema definitions. The API will process the request and return the updated address details.</p>
<pre class=" language-shell"><code class="prism  language-shell">curl -X PUT -H "Content-Type: application/json" -d '{
  "street": "Updated Street",
  "city": "Updated City",
  "postalCode": "Updated Postal Code",
  // Include any additional attributes to update
}' "https://stage-merchant.api.bsktpay.co//customers/{customerId}/addresses"
</code></pre>
<p><strong>Delete an address</strong></p>
<p>To delete an address, send a DELETE request to the <code>/customers/{customerId}/addresses</code> endpoint, replacing <code>{addressId}</code> with the actual ID of the address you want to delete. The API will process the request, and upon successful deletion, the address will no longer be available.</p>
<pre class=" language-shell"><code class="prism  language-shell">curl -X DELETE "https://stage-merchant.api.bsktpay.co/customers/{customerId}/addresses/{addressId}"
</code></pre>
<h2 id="basket">Basket</h2>
<p><strong>Add item to basket</strong></p>
<p>To add an item to the user’s shopping basket, send a POST request to the <code>/customers/{customerId}/baskets/product/{productId}</code> endpoint, replacing <code>{userId}</code> with the actual ID of the user. In the request body, provide the <code>productId</code> of the item to be added and specify the <code>quantity</code> of that item. The API will update the user’s basket accordingly and respond with the updated basket details.</p>
<pre class=" language-shell"><code class="prism  language-shell">curl -X POST -H "Content-Type: application/json" -d '{
  "quantity": 1
}' "https://stage-merchant.api.bsktpay.co/customers/{customerId}/baskets/product/{productId}"
</code></pre>
<p><strong>Get basket details</strong></p>
<p>To retrieve the details of a user’s shopping basket, make a GET request to the <code>/customers/{customerId}/baskets</code> endpoint. Replace <code>{userId}</code> with the actual ID of the user. The response will contain information about the items currently in the user’s basket, including product details, quantities, and the total amount.</p>
<pre class=" language-shell"><code class="prism  language-shell">curl -X GET "https://stage-merchant.api.bsktpay.co/customers/{customerId}/baskets"
</code></pre>
<p><strong>Update item quantity in basket</strong></p>
<p>To update the quantity of an item in the user’s shopping basket, send a PUT request to the <code>/customers/{customerId}/baskets/product/{productId}</code> endpoint, replacing <code>{userId}</code> with the actual ID of the user. In the request body, provide the <code>productId</code> of the item and the updated <code>quantity</code>. The API will modify the basket accordingly and respond with the updated basket details.</p>
<pre class=" language-shell"><code class="prism  language-shell">curl -X PUT -H "Content-Type: application/json" -d '{
  "quantity": 3
}' "https://stage-merchant.api.bsktpay.co/customers/{customerId}/baskets/product/{productId}"
</code></pre>
<p><strong>Remove item from basket</strong></p>
<p>To remove an item from the user’s shopping basket, send a DELETE request to the <code>/customers/{customerId}/baskets/product/{productId}</code> endpoint, replacing <code>{basketId}</code> with the actual ID of the basket and <code>{itemId}</code> with the ID of the item to be removed. The API will remove the specified item from the user’s basket and respond with the updated basket details.</p>
<pre class=" language-shell"><code class="prism  language-shell">curl -X DELETE "https://stage-merchant.api.bsktpay.co/customers/{customerId}/baskets/product/{productId}"
</code></pre>
<h2 id="order">Order</h2>
<p><strong>Get order details</strong></p>
<p>To retrieve the details of a specific order, make a GET request to the <code>/orders</code> endpoint. Replace <code>{orderId}</code> with the actual ID of the order you want to retrieve. The response will contain information such as the order status, customer details, items ordered, and other relevant information.</p>
<pre class=" language-shell"><code class="prism  language-shell">curl -X GET "https://stage-merchant.api.bsktpay.co/orders/{orderId}"
</code></pre>
<p><strong>Update order status - Inprogess</strong></p>
<p>To update the status of an order, send a PUT request to the <code>/stores/{storeId}/orders/{orderId}/status</code> endpoint, replacing <code>{orderId}</code> with the actual ID of the order. Include the updated status in the request body as <code>"status": "shipped"</code>. The API will update the order status accordingly and respond with the updated order details.</p>
<pre class=" language-shell"><code class="prism  language-shell">curl -X PUT -H "Content-Type: application/json" -d '{
  "status": "shipped"
}' "https://stage-merchant.api.bsktpay.co/stores/{storeId}/orders/{orderId}/status"
</code></pre>
<p><strong>Cancel an order  - Inprogess</strong></p>
<p>To cancel an order, send a DELETE request to the <code>/api/orders/{orderId}</code> endpoint, replacing <code>{orderId}</code> with the actual ID of the order you want to cancel. The API will process the cancellation request, and upon successful cancellation, the order will no longer be available.</p>
<pre class=" language-shell"><code class="prism  language-shell">curl -X DELETE "https://stage-merchant.api.bsktpay.co/orders/{orderId}"
</code></pre>

