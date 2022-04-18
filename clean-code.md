build-lists: true
presenter-notes: text-scale(1), alignment(left|right|center), Helvetica

# [fit] Writing Clean Code

## _for Humans_

[.footer: _Women Coding The Future - Online, April 2022_]

^ This is a presenter note.

---

## **Gift Egwuenu**

#### @lauragift_
#### _Developer Advocate, Cloudflare_

---

## [fit] Why Does Clean Code _Matter?_

---

✅ A good way to keep your code maintainable?

---

✅ Its a good practice when you work with a large team?

---

### How do you classify _Bad Code?_

---

![inline](https://res.cloudinary.com/lauragift/image/upload/v1650297133/clean-code-image_sqeerl.png)

Shh... Code Review In Progress!

---

## What's wrong with this code?

[.code-highlight: all]
[.code-highlight: 2]
[.code-highlight: 3]
[.code-highlight: 2-5]

```js
// sending get request to Shopify Admin API
const x = await Shopify.Utils.loadCurrentSession(req, res);
const y = new Shopify.Clients.Rest(x.shop, x.accessToken);

const products = await y.get({
  path: 'products',
});

```
---
## Better EXAMPLE

[.code-highlight: 2-5]

```js
// sending get request to Shopify Admin API
const session = await Shopify.Utils.loadCurrentSession(req, res);
const client = new Shopify.Clients.Rest(session.shop, session.accessToken);

const products = await client.get({
  path: 'products',
});
```
---

### Bad code is code that is _difficult_ to understand and creates _technical debt._

---

### _No one understands it except the_ person _who wrote it._

---

![inline](https://res.cloudinary.com/lauragift/image/upload/v1650296868/IMG_1840.jpg_cbsffn.jpg)

What bad code looks like.

---

## Later = _Never_[^⭐️]

[^⭐️]: Learn more about the [LeBlanc's Law](https://yiming.dev/clipping/2019/03/21/le-blanc's-law-a-k-a-later-equals-never/#:~:text=LeBlanc's%20Law%3A%20%22Later%20equals%20Never,fast%20you%20can%20deliver%20value.).

---
<!-- 
[.column]

![inline](https://res.cloudinary.com/lauragift/image/upload/v1650297019/FQjbylcacAIHFTH.jpeg_pszbor.jpg)

[.column]

--- -->

![inline]
(https://res.cloudinary.com/lauragift/image/upload/v1650297031/1__otRqc1VYyfa2m3enVmsuQ.png_im85be.png)

Messy code in a long term causes a lot of problems!

---

## Best Practices for Writing _Clean Code_

---

## What is _Clean Code?_

---

### _Clean code is code that is_ comprehensive _and_ easy to understand.

^ Code that anyone can read and understand other than the developer who wrote it.

---

> Clean code always looks like it was written by
> **someone who cares!**

-- Michael Feathers

---

## Use Meaningful _Naming Conventions_

---

![inline](https://res.cloudinary.com/lauragift/image/upload/v1650297061/1_7LO7JEAZbo6YmN8feAVCwg_g73zqy.png)

Who else is guilty?

---

## _Use Intentional- Revealing Names_

[.code-highlight: 4-8] 

```js
// ❌ this is a bad example
import { Order } from '@shopify/shopify-api/dist/rest-resources/2022-04/index.js';

const x = await Shopify.Utils.loadCurrentSession(request, response);

const y = new Order({session: x });
y.id = 450789469;
await y.cancel({});

```
---
## _Use Intentional- Revealing Names_

[.code-highlight: 4-8]

```js
// ✅ this is a good example
import {Order} from '@shopify/shopify-api/dist/rest-resources/2022-04/index.js';

const test_session = await Shopify.Utils.loadCurrentSession(request, response);

const order = new Order({session: test_session});
order.id = 450789469;
await order.cancel({});
```

---
## _Use Pronoucable Names_

[.code-highlight: 2-3] 

```js
// ❌ this is a bad example
const yyyy = new Date('August 19, 1975 23:15:30');
const date1 = yyyy.getDate();
```
---
## _Use Pronoucable Names_

[.code-highlight: 2-3] 

```js
// ✅ this is a good example
const birthday = new Date('August 19, 1975 23:15:30');
const date = birthday.getDate();
```
---

## Write Clean _Functions_

---
FUNCTIONS SHOULD __DO ONE THING.__ THEY SHOULD __DO IT WELL.__
THEY SHOULD __DO IT ONLY.__

---

### FUNCTION SHOULD DO JUST ONE THING

[.code-highlight: none] 
[.code-highlight: 2-6] 

```js
// ❌ this is a bad example
function getCustomer(customer) {
	const customerName = prompt("What is your name?");
	console.log(`Hello ${customerName}! How are you?`);

  const customerAddress = prompt("What is your address?");
	console.log(`My address is: ${customerAddress}.`);
}

return getCustomer();

```
---

### FUNCTION SHOULD DO JUST ONE THING

[.code-highlight: all] 

```js
// ✅ this is a good example
function getCustomerName(customer) {
	const customerName = prompt("What is your name?");
	console.log(`Hello ${customerName}! How are you?`);
}

function getCustomerAddress(customer) {
  const customerAddress = prompt("What is your address?");
	console.log(`My address is: ${customerAddress}.`);
}

```

---
## Good _Code Comments_

---

![inline](https://res.cloudinary.com/lauragift/image/upload/v1650297074/1_JokD47K7oc3WPCcY86dKww_rzlcgx.jpg)

---

### ❌ BAD COMMENT EXAMPLES
---
### _Never Explain what the code is doing_

```js
// Load the current session to get the `accessToken`.
const session = await Shopify.Utils.loadCurrentSession(req, res);
// Create a new client for the specified shop.
const client = new Shopify.Clients.Rest(session.shop, session.accessToken);
// Use `client.get` to request the specified Shopify REST API endpoint, in this case `products`.
const products = await client.get({
  path: 'products',
});
```

---
### _Remove Commented Code_

```js
const adminApiClient = new Shopify.Clients.Rest(
  session.shop,
  session.accessToken,
);

// const storefrontTokenResponse = await adminApiClient.post({
//   path: 'storefront_access_tokens',
//   type: DataType.JSON,
//   data: {
//     storefront_access_token: {
//       title: 'This is my test access token',
//     },
//   },
// });
```

---

### _Avoid Journal Comments_

[.code-highlight: 1-4]
```js
/**
 * 2022-04-20: Removed call to GraphQL Endpoint, will do that later (GE)
 * 2022-04-01: Improved Code Quality (JP)
 */
const storefrontAccessToken: string;
const session = await Shopify.Utils.loadCurrentSession(req, res);
// StorefrontClient takes in the shop url and the Storefront Access Token for that shop.
const client = new Shopify.Clients.Storefront(
  session.shop,
  storefrontAccessToken,
);
});
```

---

### ✅ Good Comment Examples

---
### _Legal Comments_

[.code-highlight: 1-7]
```js
/*
  @licstart 
     Copyright (©) 2017 My[Company]Name
     Available under the terms of the GNU/LGPL-3.0
     See LICENSE file for more informations.
  @licend 
*/
const storefrontAccessToken: string;
const session = await Shopify.Utils.loadCurrentSession(req, res);

const client = new Shopify.Clients.Storefront(
  session.shop,
  storefrontAccessToken,
);
});
```

---
### _JSDOC Comments_

[.code-highlight: 1-6]
```js
/**
 * Storefront POST API.
 * @constructor
 * @param {string} req - The request object
 * @param {string} res - The response object
 */
const storefrontAccessToken: string;
const session = await Shopify.Utils.loadCurrentSession(req, res);

const client = new Shopify.Clients.Storefront(
  session.shop,
  storefrontAccessToken,
);
});
```
---

### _TODO Comments_

[.code-highlight: 1]
```js
// TODO: Implement request to GraphQL endpoint
const storefrontAccessToken: string;
const session = await Shopify.Utils.loadCurrentSession(req, res);

const client = new Shopify.Clients.Storefront(
  session.shop,
  storefrontAccessToken,
);
});
```
---

## Formatting _/ Style Guide_

---


![inline](https://res.cloudinary.com/lauragift/image/upload/v1650310958/Screenshot_2022-04-18_at_21.19.28_guz6ky.png)

JS Standard Style, Airbnb Style Guide etc..

---

## _Follow Consistent Style_

[.code-highlight: 2-9] 

```js
// ❌ this is a bad example
const DAYS_IN_WEEK = 7;
const daysInMonth = 30;

function eraseDatabase() {}
function restore_database() {}

class animal {}
class Alpaca {}
```

---

## _Follow Consistent Style_

[.code-highlight: 2-3] 
[.code-highlight: 5-6] 
[.code-highlight: 8-9] 

```js
// ✅ this is a good example
const DAYS_IN_WEEK = 7;
const DAYS_IN_MONTH = 30;

function eraseDatabase() {}
function restoreDatabase() {}

class Animal {}
class Alpaca {}
```

---

## TDD _Principles_

---
## _LAWS OF TDD_

- Write production code only to pass a failing unit test.
- Write no more of a unit test than sufficient to fail (compilation failures are failures).
- Write no more production code than necessary to pass the one failing unit test.

---

Good tests should follow the _FIRST principle:_

F = Fast

i = Independent

R = Repeatable

S = Self Validating

T = Timely

---

## Error _Handling_

---

### Bad Code:  _Error handling with try, catch expections_

[.code-highlight: 2-6]

```js
app.post('/webhooks', async (req, res) => {
  try {
    await Shopify.Webhooks.Registry.process(req, res);
  } catch (error) {
    // ❌ this is not sufficient
    console.log(error);
  }
});
```
---

### Good Code: _Error handling with try, catch expections_

[.code-highlight: 6-9]

```js
app.post('/webhooks', async (req, res) => {
  try {
    await Shopify.Webhooks.Registry.process(req, res);
  } catch (error) {
    // ✅ this is better
    console.log(error);
    notifyUserOfError(error);
    reportErrortoService(error);
  }
});
```

---

# Clean Code _Principles_

---

## K.I.S.S

### _Keep it Simple, Stupid_

---

### D.R.Y

### _Don't Repeat Yourself_

---

![inline](https://res.cloudinary.com/lauragift/image/upload/v1650297101/1_QemPnfHFxtlZhJRRdxna2Q_fxvsg0.jpg)

_W.E.T ( We enjoy typing!)_

---

### Y.A.G.N.I

### _You ain't gonna need it_

---

![inline](https://res.cloudinary.com/lauragift/image/upload/v1650297085/sketch_fbv0q2.png)

YAGNI PRINCIPLE

---

## Boy's Scout Rule

---

### _”Always leave the_ code cleaner _than you found it”_

---

## _How You Can Tell Your Code is Clean?_

- Can someone else read this and understand what I wrote?
- How easy is it going to be to add new features further down the line?
- Do you constantly break existing functionality when making changes?

^ Ask yourself these questions

^The consequence of writing bad code can be seen if you answer mostly no’s to these questions. It means there’s some work to be done to make your code cleaner and easy for anyone to pick up and understand.
On the other hand, if your responses to these questions were all positive, then you’re doing something right and you should keep it going!

---

# RECAP

---
## _Best Practices for Writing Clean Code_

- Use meaningful naming conventions
- Write clean functions
- Good code comments
- Format and use a style guide
- Follow TDD principles
- Handle errors correctly

---

## _Clean Code Principles_

- K.I.S.S
- D.R.Y
- Y.A.G.N.I
- Boy's Scout Rule

---

## Remember:

### _"Always leave the code cleaner than you found it"_

---

## What to do next?

---

# _Resources_

- [Clean Code Book - Robert Martin](https://www.oreilly.com/library/view/clean-code-a/9780136083238/)
- [Code Complete - Steve McConnell](https://www.oreilly.com/library/view/code-complete-2nd/0735619670/)
- [Introduction to Clean Code and Software Design Principles](https://workat.tech/machine-coding/tutorial/introduction-clean-code-software-design-principles-nwu4qqc63e09)
- [Writing Clean Code for Humans - Cory House](https://www.pluralsight.com/courses/writing-clean-code-humans)
  
---

# **Thank you!**

#### *@lauragift_*