---
title: API Reference

language_tabs:
  - shell

toc_footers:
  - <a href='https://optimizeplayer.com'>optimizeplayer.com</a>

includes:
  - folders
  - integrations
  - ctas
  - cta_button
  - cta_optin
  - cta_social
  - cta_tag
  - cta_purchase
  - cta_survey
  - cta_html
  - cta_trigger
  - errors

search: true
---

# Introduction

Welcome to the OptimizePlayer API!

# Authentication

> To authorize, add api_key field to query parameters:

```shell
curl "api_endpoint_here"
 -d api_key=test_key
```

> Make sure to replace `test_key` with your API key.

OptimizePlayer Api uses API keys to allow access to the API.
OptimizePlayer Api expects for the API key to be included in all API requests to the server in a query parameters that looks like the following:

`api_endpoint_here?api_key=test_key`

<aside class="notice">
You must replace <code>test_key</code> with your personal API key.
</aside>
