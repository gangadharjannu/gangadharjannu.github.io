---
title: "Parse XML content in Express, NodeJS"
date: 2024-03-03T23:47:21.300Z
description: "Parse XML content in NodeJS using Express and body-parser middleware"
---

Recently, I've been working on a pet project involving an XML feed that I need to handle with my NodeJS and Express server. It took me some time to figure out how to parse the XML data. I found that there wasn’t a lot of information available on parsing XML content, which might suggest that it’s not a widely used technique.

Recently I worked on a pet project where I receive an XML feed that I need to handle with my NodeJS and Express server. It took me a while to figure out how to parse the XML data.

## Parsing XML content using Express

Express relies on the body-parser middleware to handle and parse incoming request bodies, making the data accessible to route handlers.

While I typically use JSON and urlencoded middlewares for parsing request content, handling other data types in Express requires using the Raw body parser or the Text body parser [^1].

The Raw body parser produces binary or buffer data, whereas the Text body parser outputs plain text.

In my case, I opted for the Text body parser because I need to retain the original XML data from incoming requests.

### Implementation

Initially, I attempted to use `app.use(express.text())`, but it resulted in an empty object. To resolve this, I needed to specify the `type` option in the `express.text` function as follows:

```javascript
app.use(express.text({ type: "*/*" }))
```

This configuration successfully parsed the XML content and populated the `req.body` property with it.

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
