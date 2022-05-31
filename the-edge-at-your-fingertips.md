build-lists: true presenter-notes: text-scale(.7), alignment(left), Futura
slide-transition: true


## [fit] The __EDGE__ at your Fingertips,
## Literally!

[.footer: _JSWorld Conference - Amsterdam, June 2022_]
[.footer-style: #2F2F2F, alignment(center), text-scale(1.5)]
---
## What we'll cover?

- What is the Edge?
- How is it different from Serverless Functions?
- Pros & Cons of Serverless & Edge functions.
- The Cloudflare Developer Ecosystem.
- Use Cases and Examples.

[.header: alignment(left), text-scale(1.0)]
[.list: bullet-character(•), alignment(left)]
[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]

---

![right](./images/gift3.jpeg)

# Gift Egwuenu
### Developer Advocate @Cloudflare
### _Educator_ & _Youtuber_
#### *@lauragift_*
[.header: alignment(left), text-scale(1.0)]
[.text: alignment(left), text-scale(1.0)]
---
# [fit] _What is the_ __Edge___?_

[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---
<!-- # [fit] _The Edge at your fingertips, Literally!_

[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
--- -->

The edge is a server **geographically** located 
close to your **users**.

[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---

![original](./images/pop.png)

<!-- [.header: #ddd, alignment(center), text-scale(0.8)] -->
---

### **Where it all started...**
[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---
![](./images/home%20server.jpeg)

--- 
![](./images/home%20server.jpeg)
![](./images/server.jpeg)

--- 
![](./images/home%20server.jpeg)
![](./images/server.jpeg)
![](images/server2.jpeg)

---
# Limitations of Traditional Servers

- Host your own server.
- High latency.
- Limited opportunity for scaling.
- Expensive to maintain.
  
[.header: alignment(left), text-scale(1.0)]
[.list: bullet-character(•), alignment(left)]
[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---

## Serverless Functions

[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---

![](./images/serverless.png)

---
## Advantages of Serverless Functions
- Hosted by a provider, no need to manage your servers.
- Low Costs of Bandwidth.
- Scalibility On Demand.

[.header: alignment(left), text-scale(1.0)]
[.list: bullet-character(•), alignment(left)]
[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---
## Limitation of Serverless Functions
- All functions are stored in a  centralized core location (us-east1).
- Cold starts after the function is idle. 
- Debugging and Testing is challenging.
  
[.header: alignment(left), text-scale(1.0)]
[.list: bullet-character(•), alignment(left)]
[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---

## Edge Functions
[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]

---
## Edge Functions

### _=_
### **Serverless Functions at The Edge**

[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---

## Advantages of Edge Functions
- Reduced Latency
- Zero Cold Start
- Improves Application Performace

[.header: alignment(left), text-scale(1.0)]
[.list: bullet-character(•), alignment(left)]
[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---

## Limitations of Edge Functions
- Low Latency due to Data Storage 
  
[.header: alignment(left), text-scale(1.0)]
[.list: bullet-character(•), alignment(left)]
[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---

## Cloudflare Developer Platform

![inline 90%](images/dev-platform.png)

[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---

### ![inline 100%](images/workers.jpeg) Cloudflare Workers

[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---

**Cloudflare Workers** provides a serverless execution environment that allows you to create entirely new applications or augment existing ones without configuring or maintaining infrastructure.

---

- Goodbye to cold starts—support for **0ms** worldwide.
  
[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---

How is a zero cold start possible?

![inline fit](images/workers-handshake.png)

---

How is a zero cold start possible?

![inline fit](images/layer.png)

---
- Cost Savings - **100,000** request/daily free & affordable plans to scale.
  
[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---

- Edge Storage with KV, Durable Object, R2 & D1.

[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---

#### ![inline 40%](images/workers.jpeg) Cloudflare Workers 
### How It Works?

[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---

- V8 Isolates Engine

[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---

![inline 70%](images/isolates.png)

[.header: #222, line-height(8)]
[.background-color: #FFF]

---

- Computer per Request
  
[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---

## Worker Example

```js
export default {
  fetch() {
    return new Response('Hello world');
  },
};
```
[.header: alignment(left)]
[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---

- Distrubuted Execution
  
[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---

### ![inline 30%](images/pages.png) Pages Functions

[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---

**Pages Functions** enable you to run server-side code in your application to enable dynamic functionality without running a dedicated server. 

[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---
```js
export async function onRequestPost(request) {
  return new Response(`Hello world`);
}
```
[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---
## Functions Routing (Beta)

[.code-highlight: none]
[.code-highlight: 2-3]
[.code-highlight: all]

```bash
├── ...
├── functions
|   └── api
│       ├── [[path]].ts
│       ├── [username]
│       │   └── profile.ts
│       ├── time.ts
│       └── todos
│           ├── [[path]].ts
│           ├── [id].ts
│           └── index.ts
└── ...
```
[.code: auto(42), Font Family Name, line-height(1.5)]
[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---

![](images/data.jpeg)
### Data Storage on the Edge

[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---

![INLINE 120%](images/twitter.png)

[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]

---

###  Workers KV

[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---

Workers KV is a global, low-latency, key-value data store.

---

```js
await NAMESPACE.put(key, value);
```

[.code: alignment(center)]
[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---


```js
await NAMESPACE.get(key);
```

[.code: alignment(center)]
[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---


```js
await NAMESPACE.delete(key);
```

[.code: alignment(center)]
[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---


```js
await NAMESPACE.list();
```

[.code: alignment(center)]
[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---

### Durable Objects

[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---

**Durable Objects** provide **low-latency** coordination and consistent storage for the Workers platform through two features -
**global uniqueness and a transactional storage API.**

[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---

```js
export class DurableObject {
  constructor(state, env) {}

  async fetch(request) {
    return Response("Hello World")
  }
}
```

[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---

### R2

[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---

R2 storage allows developers to store large amounts of unstructured data without the costly egress bandwidth fees associated with typical cloud storage services.

[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---
##  R2 Bindings
```toml
# wrangler.toml
[[r2_buckets]]
binding = 'MY_BUCKET' # <~ valid JavaScript variable name
bucket_name = '<YOUR_BUCKET_NAME>'
```
[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---

![fit](images/d1.png)

---
### Example Use Cases

- Real-time application with Durable Objects and Workers
- A/B Testing
- Custom HTTP Headers & Cookie Management
- IOT/Gaming
- User Authentication and Authourization
- Geolocation Use cases
- Compliance
- Localization and Personalization

[.header: alignment(left), text-scale(1.0)]
[.list: bullet-character(•), alignment(left)]
[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---

### When **not** to use Cloudflare Workers

![inline fit](add gif about using it everytime)
  
[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---

### When **not** to use Cloudflare Workers

- Database is not hosted on the Edge!
- More ???

[.list: bullet-character(•), alignment(center)]
[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---

### **Workers Examples**

[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---

## Geolocation Based Redirects

[.code-highlight: none]
[.code-highlight: 3]
[.code-highlight: 4-7]
[.code-highlight: all]

```js
export default {
  async fetch(request: Request): Promise<Response> {

    const { cf } = request
    if ( cf?.country === "NL") {
      return Response.redirect("https://cloudflare.com")
    }
  },
};
```

[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---

![right fit autoplay mute](./images/geolocation.mov)
## Geolocation Based Redirects

```js
export default {
  async fetch(request: Request): Promise<Response> {
    const { cf } = request
    if ( cf?.country === "NL") {
      return Response.redirect("https://cloudflare.com")
    }
  },
};
```
---

## Retry/Log Failed requests

[.code-highlight: none]
[.code-highlight: 3]
[.code-highlight: all]

```javascript
export default {
  async fetch(request: Request): Promise<Response> {
    const res = await fetch("https://httpstat.us/503?sleep=2000")

    if (!res.ok) {
      return await fetch("https://httpstat.us/200")
    } else {
      return res
    }
  }
}
```

[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---

## Retry/Log Failed requests

![right fit autoplay mute](./images/retry.mov)

```javascript
export default {
  async fetch(request: Request): Promise<Response> {
    const res = await fetch("https://httpstat.us/503?sleep=2000")

    if (!res.ok) {
      return await fetch("https://httpstat.us/200")
    } else {
      return res
    }
  }
}

```
---

## A/B Testing Remote Origins

[.code-highlight: none]
[.code-highlight: 4-5]
[.code-highlight: 6]
[.code-highlight: 7-11]
[.code-highlight: all]

```js
export default {
  async fetch(request: Request): Promise<Response> {

    const origin1 = 'https://cloudflare.com';
    const origin2 = 'https://jsworldconference.com';
    const randomNumber = Math.floor(Math.random() * 100) + 1;

    if (randomNumber > 50) {
      return fetch(origin1);
    } else {
      return fetch(origin2);
    }
  },
};
```
[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---

![right fit autoplay mute](./images/ab.mov)

## A/B Testing Remote Origins

```js
export default {
  async fetch(request: Request): Promise<Response> {

    const origin1 = 'https://cloudflare.com';
    const origin2 = 'https://jsworldconference.com';
    const randomNumber = Math.floor(Math.random() * 100) + 1;

    if (randomNumber > 50) {
      return fetch(origin1);
    } else {
      return fetch(origin2);
    }
  },
};
```
---

## What we've learned today?

- What is the Edge?
- How is it different from Serverless Functions?
- Pros & Cons of Serverless & Edge functions.
- The Cloudflare Developer Ecosystem (Workers, KV, R2, DO, D1).
- Use Cases & Examples of Edge Functions.

[.header: alignment(left), text-scale(1.0)]
[.list: bullet-character(•), alignment(left)]
[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]

---

Building applications on the **Edge** brings us 
closers to the end-users, improving 
the **user's experience** and 
making the web more **accessible**.

[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
---
![right 100%](./images/frame.png)
## Further Resources

- [Cloudflare Workers Documentation](https://developers.cloudflare.com/workers/)
- [Cloudflare Pages Documentation](https://developers.cloudflare.com/pages/)
- Cloudflare Blog - [blog.cloudflare.com](https://blog.cloudflare.com/)
- [Cloudflare Devs Discord](https://discord.com/invite/cloudflaredev/)

[.header: alignment(left), text-scale(1.0)]
[.list: bullet-character(•), alignment(left)]
---
# Thank you!

[.footer: *@lauragift_*]
[.footer-style: alignment(right), text-scale(1.5)]
