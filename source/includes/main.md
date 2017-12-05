# Introduction

Welcome to the anthq public API! You can use our API to build custom or reusable apps that have access most resources on Ant. 

This documentation is still in the early phases.

# Authentication

Please request API keys from avin@anthq.com

Ant uses Basic Auth to process asyncronous events to its ingest server.

```bash
  curl "https://ingest.anthq.com/v3/endpoint" -H 
  Basic NDM5NzYwMTItZDU1NC00NT==
  App-Instance-GUID f2eaeb7d-c918-41c6-96dd-b79660ff629a
  Content-Type application/json
```

# Webhooks

## Creating a new product

```json
  {
    product: {
      "id":303500,
      "sku":"30946",
      "name":"Madeleine Thompson Annette Jumper",
      "description":"<p>Annette Top by Madeleine Thompson. Cream cashmere long sleeve Jumper.</p>\n<p>&nbsp;</p>\n<p>Featuring blue, navy and orange V shape stripes creating an illusion on the neckline. 100% Cashmere. Dry clean only. Color: white</p>\n",
      "short_description":"",
      "full_price":0.0,
      "whole_sale_price":0.0,
      "franchise_price":0.0,
      "markup":0.0,
      "tax":0.0,
      "weight":0.0,
      "vendor":null,
      "supplier":null,
      "brand":null,
      "handle":"Madeleine-Thompson-Annette-Jumper-ziqc",
      "special":null,
      "tags":[],
      "product_type":null,
      "manage_stock":true,
      "product_errors":null,
      "images":[
        {
          "id":562329,
          "url":"https://images.anthq.com/aa6b512a-a383-435d-bba0-7914a2beb287/7532a8fb-6e95-4c66-9bcc-12f3aab21620-T13_ANNETTE.jpg",
          "position":1
        {
          "id":562330,
          "url":"https://images.anthq.com/aa6b512a-a383-435d-bba0-7914a2beb287/c315e25f-726f-40fe-9bf8-12f0b08d14f3-MT_AW17_LOOKBOOK_P02_MAUDA_PANT_T13_ANNETTE_JUMPER_1873_.jpg",
          "position":2
      "variants":[
        {
          "id":708499,
          "sku":"30946",
          "full_price":280.0,
          "product_id":303500,
          "product_name":"Madeleine Thompson Annette Jumper",
          "coupled":true,
          "whole_sale_price":0.0,
          "franchise_price":0.0,
          "markup":0.0,
          "variant_string":"LARGE",
          "option_string":"Size",
          "tax":46.67,
          "position":1,
          "weight":0.0,
          "inventories":[
            {
              "id":2507894,
              "quantity":0,
              "outlet_id":523,
              "outlet_name":"Main Outlet",
              "enabled":true
            }
          ],
          "options":[
            {
              "code":"Size", 
              "value":"LARGE"
            }
          ]
        },
        {
          "id":708500,
          "sku":"30944",
          "full_price":280.0,
          "product_id":303500,
          "product_name":"Madeleine Thompson Annette Jumper",
          "coupled":null,
          "whole_sale_price":0.0,
          "franchise_price":0.0,
          "markup":0.0,
          "variant_string":"SMALL",
          "option_string":"Size",
          "tax":46.67,
          "position":2,
          "weight":0.0,
          "inventories":[
            {
              "id":2507895,
              "quantity":0,
              "outlet_id":523,
              "outlet_name":"Main Outlet",
              "enabled":true
            }
          ],
          "options":[
            {
              "code":"Size", 
              "value":"SMALL"
            }
          ]
        },
        {
          "id":708501,
          "sku":"30945",
          "full_price":280.0,
          "product_id":303500,
          "product_name":"Madeleine Thompson Annette Jumper",
          "coupled":null,
          "whole_sale_price":0.0,
          "franchise_price":0.0,
          "markup":0.0,
          "variant_string":"MEDIUM",
          "option_string":"Size",
          "tax":46.67,
          "position":3,
          "weight":0.0,
          "inventories":[
            {
              "id":2507896,
              "quantity":0,
              "outlet_id":523,
              "outlet_name":"Main Outlet",
              "enabled":true
            }
          ],
          "options":[
            {
              "code":"Size", 
              "value":"MEDIUM"
            }
          ]
        }
      ],
      "product_options":[
        {
          "id":201576,
          "product_id":303500,
          "name":"Size",
          "position":1,
          "values":[
            {
              "id":708900,
              "product_option_id":201576,
              "name":"LARGE",
              "position":1
            },
            {
              "id":708901,
              "product_option_id":201576,
              "name":"SMALL",
              "position":2
            },
            {
              "id":708902,
              "product_option_id":201576,
              "name":"MEDIUM",
              "position":3
            }
          ]
        }
      ],
      "meta":[]
    },
    meta: {
      <application specific metadata>
    }
  }
```

Product update/create and delete events are sent as following

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
async | false | If set to true, the webhook won't expect a response with updated values

## Updating a product

```json
  {
    product: {
      "id":303500,
      "sku":"30946",
      "name":"Madeleine Thompson Annette Jumper",
      "description":"<p>Annette Top by Madeleine Thompson. Cream cashmere long sleeve Jumper.</p>\n<p>&nbsp;</p>\n<p>Featuring blue, navy and orange V shape stripes creating an illusion on the neckline. 100% Cashmere. Dry clean only. Color: white</p>\n",
      "short_description":"",
      "full_price":0.0,
      "whole_sale_price":0.0,
      "franchise_price":0.0,
      "markup":0.0,
      "tax":0.0,
      "weight":0.0,
      "vendor":null,
      "supplier":null,
      "brand":null,
      "handle":"Madeleine-Thompson-Annette-Jumper-ziqc",
      "special":null,
      "tags":[],
      "product_type":null,
      "manage_stock":true,
      "product_errors":null,
      "images":[
        {
          "id":562329,
          "url":"https://images.anthq.com/aa6b512a-a383-435d-bba0-7914a2beb287/7532a8fb-6e95-4c66-9bcc-12f3aab21620-T13_ANNETTE.jpg",
          "position":1,
          "remote_id":"30335",
          "remote_url":
          "https://baarandbass.com/wp-content/uploads/2017/09/T13_ANNETTE.jpg"},
        {
          "id":562330,
          "url":"https://images.anthq.com/aa6b512a-a383-435d-bba0-7914a2beb287/c315e25f-726f-40fe-9bf8-12f0b08d14f3-MT_AW17_LOOKBOOK_P02_MAUDA_PANT_T13_ANNETTE_JUMPER_1873_.jpg",
          "position":2,
          "remote_id":"30331",
          "remote_url":
          "https://baarandbass.com/wp-content/uploads/2017/09/MT_AW17_LOOKBOOK_P02_MAUDA_PANT_T13_ANNETTE_JUMPER_1873_.jpg"}],
      "variants":[
        {
          "id":708499,
          "sku":"30946",
          "full_price":280.0,
          "product_id":303500,
          "product_name":"Madeleine Thompson Annette Jumper",
          "coupled":true,
          "whole_sale_price":0.0,
          "franchise_price":0.0,
          "markup":0.0,
          "variant_string":"LARGE",
          "option_string":"Size",
          "tax":46.67,
          "position":1,
          "weight":0.0,
          "inventories":[
            {
              "id":2507894,
              "quantity":0,
              "outlet_id":523,
              "outlet_name":"Main Outlet",
              "enabled":true
            }
          ],
          "options":[
            {
              "code":"Size", 
              "value":"LARGE"
            }
          ],
          "remote_id":"30352",
          "remote_url":null
        },
        {
          "id":708500,
          "sku":"30944",
          "full_price":280.0,
          "product_id":303500,
          "product_name":"Madeleine Thompson Annette Jumper",
          "coupled":null,
          "whole_sale_price":0.0,
          "franchise_price":0.0,
          "markup":0.0,
          "variant_string":"SMALL",
          "option_string":"Size",
          "tax":46.67,
          "position":2,
          "weight":0.0,
          "inventories":[
            {
              "id":2507895,
              "quantity":0,
              "outlet_id":523,
              "outlet_name":"Main Outlet",
              "enabled":true
            }
          ],
          "options":[
            {
              "code":"Size", 
              "value":"SMALL"
            }
          ],
          "remote_id":"30354",
          "remote_url":null
        },
        {
          "id":708501,
          "sku":"30945",
          "full_price":280.0,
          "product_id":303500,
          "product_name":"Madeleine Thompson Annette Jumper",
          "coupled":null,
          "whole_sale_price":0.0,
          "franchise_price":0.0,
          "markup":0.0,
          "variant_string":"MEDIUM",
          "option_string":"Size",
          "tax":46.67,
          "position":3,
          "weight":0.0,
          "inventories":[
            {
              "id":2507896,
              "quantity":0,
              "outlet_id":523,
              "outlet_name":"Main Outlet",
              "enabled":true
            }
          ],
          "options":[
            {
              "code":"Size", 
              "value":"MEDIUM"
            }
          ],
          "remote_id":"30353",
          "remote_url":null
        }
      ],
      "product_options":[
        {
          "id":201576,
          "product_id":303500,
          "name":"Size",
          "position":1,
          "values":[
            {
              "id":708900,
              "product_option_id":201576,
              "name":"LARGE",
              "position":1
            },
            {
              "id":708901,
              "product_option_id":201576,
              "name":"SMALL",
              "position":2
            },
            {
              "id":708902,
              "product_option_id":201576,
              "name":"MEDIUM",
              "position":3
            }
          ]
        }
      ],
      "meta":[],
      "remote_id":"30351",
      "remote_url":
      "https://baarandbass.com/product/madeleine-thompson-annette-jumper/"},
    meta: {
      <application specific metadata>
    }
  }
```

This endpoint updates a product that already exists on a remote app. Ant stores key ids so you don't have to query the remote application.

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
async | false | If set to true, the webhook won't expect a response with updated values


## Importing products

```json
  {
    products: {
      page: 1
      page_size: 25
    }
  }
```

Expects a response

```json
  {
    product: {
      page: 1
      page_size: 25
    }
  }
```
