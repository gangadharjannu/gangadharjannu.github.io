---
title: "Uint8array to String and String to Uint8array in Browser and NodeJS"
date: 2023-10-26T01:22:45+02:00
description: "Convert Uint8array to String and String to Uint8array in Browser and NodeJS"
---

Recently, I worked on an Ethereum project where I needed to store a secret in the form of a `Uint8Array`. To do this, I first had to convert the `Uint8Array` into a string and then convert it back to `Uint8Array` when needed.

Once converted to a string, the secret can be stored either on the server or locally (for development purposes only).

## In browser

### Uint8Array to string

```javascript
// Given `secret` is of type Uint8Array
const str = btoa(secret);
// The `str` can now be shared with the server via an API call
// or stored locally (for development purposes only)
```

### string to Uint8Array

```javascript
// Assuming `str` is a string that we stored previously
const stringArr = atob(str).split(",");
const secret = new Uint8Array(stringArr);
```

## In NodeJs

### Uint8Array to string

```node
let data = Buffer.from(secret).toString("base64")
```

### string to Uint8Array

```node
let uint8arr = new Uint8Array(Buffer.from(data, "base64"))
```
