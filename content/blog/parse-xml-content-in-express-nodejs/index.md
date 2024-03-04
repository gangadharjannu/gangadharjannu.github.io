---
title: "Parse XML content in Express, NodeJS"
date: 2024-03-03T23:47:21.300Z
description: "Parse XML content in NodeJS using Express and body-parser middleware"
---

Recently I am working on a pet project where I will receive a XML feed information to my NodeJS and Express server and it took me a while to figure out how to parse XML.

There wasn't much information available related to parsing XML content, may be not much people are using ?

## Parsing XML content using Express

Express uses body-parser middleware to parse incoming request bodies and make it available to route handlers.

So we mostly use JSON and urlencoded middlewares to parse content from requests however, if you want to read other data types using Express, we need to use the existing Raw body parser or Text body parser [^1].

Raw body parser outputs Binary/buffer data while Text body parser emits plain text.

I have used Text body parser since I need the original incoming XML.

### Implementation

I initially tried using `app.use(express.text())` which resulted in an empty object. To fix that I had to specify `type` option in `express.text` function like below

`app.use(express.text({ type: "*/*" }))`

This successfully parsed XML content and added it on `req.body` property.

### Full implementation

```JavaScript
const express = require("express");

const port = 3000;
const app = express();

app.use(express.text({type: "*/*"}));

app.post("/", (req, res) => {
  console.log("POST");
  console.log(req.body);
});

app.listen(port, () => {
  console.log(`Example app listening on port ${port}`);
});
```

#### References

[^1]: <https://expressjs.com/en/resources/middleware/body-parser.html>
