# node-payant
A nodejs API for [Payant](https://payant.ng).

### Installation
```js
npm install node-payant
```

### Features
- Promisified
- Callback chaining with promise handlers


### Parameters For Each Call
|  Resource/method       |   Ref   |   params   |   
|------------------------|---------|------------|
| **Clients.add**        | Nil     |  Yes - `firstname, lastname, email, phone` |
| **Clients.get**        | Yes     | Nil        |
| **Clients.edit**       | Yes     | Yes - `firstname, lastname, email, phone`  |
| **Clients.delete**     | Yes     | Nil        |
| | | |
| **Invoices.add**       | Nil     | Yes - `firstname, lastname, email, phone` or `client_id, due_date, fee_bearer, items` |
| **Invoices.get**       | Yes     | Nil        |
| **Invoices.send**      | Yes     | Nil        |
| **Invoices.history**   | Nil     | Yes - `period` |
| **Invoices.delete**    | Yes     | Nil        |
| | | |
| **misc.getBanks**      | Nil     | Nil        |
| | | |
| **Payments.create**    | Nil     | Yes - `reference_code, date, amount, channel` |
| **Payments.get**       | Yes     | Nil        |
| **Payments.history**   | Nil     | Yes - `period` |
| | | |
| **Products.create**    | Nil     | Yes - `customer, plan`  |
| **Products.disable**   | Nil     | Yes - `code, token`     |
| **Products.enable**    | Nil     | Yes - `code, token`     |
| **Products.get**       | Yes     | Nil        |
| **Products.list**      | Nil     | Nil        |

The parameters specified in the third column are the complusory ones. But they are not limited to them alone. Check over at 
[Payant](https://developers.payant.ng) for the complete list.

### Examples
```js
// Requiring the library
const payant = require('node-payant')(secret_key);

// Adding a new client
payant.clients.add({
		data: {
				first_name: "Subomi",
				last_name: "Oluwalana",
				email: "subomi.oluwalana@yahoo.com",
				phone: "+2348077886076"
			}
		}, (error, data) => {
			if(!error) {
				return data;
			} 
			return error;
		})

// Retrieving a client's details
payant.clients.get(
		{ref: 900}, 
		(error, data) => {
			// parse response as json object
			return JSON.parse(data);
		})
		.then((value) => {}, (reason) => {});

```
### TODO
- Write Tests

### Saying Thank You
Just star, and report issues. Thank you.

