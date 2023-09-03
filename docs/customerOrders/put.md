---
sidebar_position: 1
---

# Submit new customer order batched

## Description

Saves a new orders or updates a pending order. If the packing slip number has already been processed, the message will be ignored.

This method will accept orders as a array.

## Request

-   Method: `PUT`
-   Content Type: `application/json`
-   URL: `https://api.gosweetspot.com/api/customerorders`

### Headers

-   **access_key** : your unqiue api key provided by GSS
-   **site_id** : which site you are requesting action for

### Parameters

The body of the message should be sent as an JSON array.

| Parameter        | Type        | Description                                                                                                                             |
| ---------------- | ----------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| packingslipno    | string      | Specify the unique order number from your source system, that was used as the packing slip no when the order was published              |
| consignee        | string      | recepient name                                                                                                                          |
| address1         | string      | address line 1, eg, building identifier, like Level 1, Fisher House, etc                                                                |
| address2         | string      | address line 2, street name                                                                                                             |
| suburb           | string      | suburb name                                                                                                                             |
| city             | string      | city name or state name. Depending on destination country, if state information is available, this should be the abbreviated state code |
| postcode         | string      | post code, for NZ addresses, this can be left blank if unknown                                                                          |
| country          | string      | ISO Alpha 2 country code, eg NZ, AU, US, UK, CN                                                                                         |
| delvref          | string      | Order number, or customer reference for this order                                                                                      |
| delvinstructions | string      | Any specific instructions to be printed on the label                                                                                    |
| contactname      | string      | name of person, optional                                                                                                                |
| contactphone     | string      | phone number of person, optional                                                                                                        |
| email            | string      | email address for track &amp; trace email, optional                                                                                     |
| rawaddress       | string      | full, unvalidated address body for display purposes only. Use \\n for newline in this field. Optional                                   |
| costcentre       | string      | Put the exact name of a cost centre here and the cost centre will be pre-selected when fulfilling the order. Optional                   |
| products         | object list | optional, JSON object of [product model](/docs/models/product-model.md)                                                                 |
| packages         | object list | optional, JSON object of [package model](/docs/models/customer-order-package-model.md)                                                  |
| iconUrl          | string      | optional, custom icon Url link.                                                                                                         |

## Return format

JSON object array per order with _true_ for a successfult submit or _false_ for an ignored submit

## Request example

```Curl

curl --location --globoff --request PUT 'https://api.gosweetspot.com/api/api/customerorders' \
--header 'access_key;' \
--header 'site_id;' \
--header 'Content-Type: application/json' \
--data '[
  {
    "packingslipno": "test1-14-07-01",
    "consignee": "Test 1",
    "address1": "1 Queens Street",
    "address2": "",
    "suburb": "Auckland Central",
    "city": "Auckland",
    "postcode": "",
    "country": null,
    "delvref": null,
    "delvinstructions": null,
    "contactname": null,
    "contactphone": null,
    "email": null,
    "iconUrl": null,
    "Products": [{
        "productcode": "ABC",
        "Description": "Wall Paint",
        "Units": 1.0,
        "UnitValue": 10.0,
        "CountryofManufacture": null,
        "UnitKg": 1.0,
        "ImageUrl": null,
        "Currency": "NZD"
    }, {
        "productcode": "DCF",
        "Description": "Wall Art",
        "Units": 1.0,
        "UnitValue": 10.0,
        "CountryofManufacture": null,
        "UnitKg": 1.0,
        "ImageUrl": null,
        "Currency": "NZD"
    }]
  },
  {
    "packingslipno": "test2-14-07-01",
    "consignee": "Test 2",
    "address1": "1 Queens Street",
    "address2": "",
    "suburb": "Auckland Central",
    "city": "Auckland",
    "postcode": "",
    "country": null,
    "delvref": null,
    "delvinstructions": null,
    "contactname": null,
    "contactphone": null,
    "email": null
  }
]'

```

## Response example

```Json
[
  {
    "packingslipno": "test1-14-07-01",
    "result": true,
    "msg":""
  },
  {
    "packingslipno": "test2-14-07-01",
    "result": false,
    "msg":"already processed"
  }
]
```
