---
title: "Uint8array to String and String to Uint8array in Browser and NodeJS"
date: 2023-10-26T01:22:45+02:00
draft: true
---

Recently I worked on an Ethereum project where I had to store secret which is in `Uint8Array`. To store the secret I had to convert that into string and convert it back to `Uint8Array`.

Once it is converted into string, we can store that information in either server or local (only for development)

## In browser

### Uint8Array to string

```javascript
// Considering `secret` of type Uint8Array
const str = btoa(secret);
// Now we can share the `str` with server using API call 
// or store it in our local (only for development)
```

### string to Uint8Array

```javascript
// Considering `str` of type string which we stored previously
const stringArr = atob(str).split(",")
const secret = new Uint8Array(stringArr)
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
