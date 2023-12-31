---
sidebar_position: 1
---

# List customer orders

## Description

Get the list of customer orders published to the queue. You can filter on processed or non-processed.

## Request

-   Method: `GET`
-   Content Type: `application/json`
-   URL: `https://api.gosweetspot.com/api/customerorders`

### Headers

- **access_key** : your unqiue api key provided by GSS
- **site_id** : which site you are requesting action for

### Parameters

<table><tbody><tr><th>Parameter</th><th>Type</th><th>Description</th></tr><tr><td><div>packingslipno</div><div contenteditable="false"><div><div><div></div></div></div><div></div></div></td><td><div>string</div><div contenteditable="false"><div><div><div></div></div></div><div></div></div></td><td><div>comma separated list of packing slip numbers to apply filter on</div><div contenteditable="false"><div><div><div></div></div></div><div></div></div></td></tr><tr><td><div>createdfrom</div><div contenteditable="false"><div><div><div></div></div></div><div></div></div></td><td><div>string</div><div contenteditable="false"><div><div><div></div></div></div><div></div></div></td><td><div>UTC formatted date and time to filter the shipments on. This field is for earliest date</div><div contenteditable="false"><div><div><div></div></div></div><div></div></div></td></tr><tr><td><div>createdto</div><div contenteditable="false"><div><div><div></div></div></div><div></div></div></td><td><div>string</div><div contenteditable="false"><div><div><div></div></div></div><div></div></div></td><td><div>UTC formatted date and time to filter the shipments on. This field is for latest date</div><div contenteditable="false"><div><div><div></div></div></div><div></div></div></td></tr><tr><td><div>excludecompleted</div><div contenteditable="false"><div><div><div></div></div></div><div></div></div></td><td><div>string</div><div contenteditable="false"><div><div><div></div></div></div><div></div></div></td><td><div>true/false - when true excludes all completed packing slip and only returns pending orders</div><div contenteditable="false"><div><div><div></div></div></div><div></div></div></td></tr><tr><td><div>page</div><div contenteditable="false"><div><div><div></div></div></div><div></div></div></td><td><div>integer</div><div contenteditable="false"><div><div><div></div></div></div><div></div></div></td><td><div>when multi pages of results are available specifies which page to get</div><div contenteditable="false"><div><div><div></div></div></div><div></div></div></td></tr><tr><td><div>pagesize</div><div contenteditable="false"><div><div><div></div></div></div><div></div></div></td><td><div>integer</div><div contenteditable="false"><div><div><div></div></div></div><div></div></div></td><td><div>how many records to return per page. Default = 100 records</div><div contenteditable="false"><div><div><div></div></div></div><div></div></div></td></tr><tr><td><div>includeProducts</div><div contenteditable="false"><div><div><div></div></div></div><div></div></div></td><td><div>boolean</div><div contenteditable="false"><div><div><div></div></div></div><div></div></div></td><td><div>true/false - when true, each customer order record will also include the product lines associated with the record.</div><div contenteditable="false"><div><div><div></div></div></div><div></div></div></td></tr></tbody></table>

## Return format

A JSON Object of available carriers.

### Root Object

<table><tbody><tr><th>Attribute</th><th>Type</th><th>Description</th></tr><tr><td><div>Page</div><div contenteditable="false"><div><div><div></div></div></div><div></div></div></td><td><div>integer</div><div contenteditable="false"><div><div><div></div></div></div><div></div></div></td><td><div>index of the page of all results</div><div contenteditable="false"><div><div><div></div></div></div><div></div></div></td></tr><tr><td><div>pagesize</div><div contenteditable="false"><div><div><div></div></div></div><div></div></div></td><td><div>integer</div><div contenteditable="false"><div><div><div></div></div></div><div></div></div></td><td><div>how many records to return per page.</div><div contenteditable="false"><div><div><div></div></div></div><div></div></div></td></tr><tr><td><div>Pages</div><div contenteditable="false"><div><div><div></div></div></div><div></div></div></td><td><div>integer</div><div contenteditable="false"><div><div><div></div></div></div><div></div></div></td><td><div>how many pages of results are available</div><div contenteditable="false"><div><div><div></div></div></div><div></div></div></td></tr><tr><td><div>Results</div><div contenteditable="false"><div><div><div></div></div></div><div></div></div></td><td><div>object list</div><div contenteditable="false"><div><div><div></div></div></div><div></div></div></td><td><div>list of <a href="/docs/models/Customer-Order-Model" target="_self">customer orders</a></div><div contenteditable="false"><div><div><div></div></div></div><div></div></div></td></tr></tbody></table>

## Request example

```Curl

curl --location 'https://api.gosweetspot.com/api/customerorders?createdfrom=2023-08-01&page=2' \
--header 'access_key;' \
--header 'site_id;' \
--header 'Content-Type: application/json; charset=utf-8'

```

## Response example

```Json
{
    "Page": 1,
    "PageSize": 100,
    "Pages": 6,
    "Results": [
        {
            "packingslipno": "SSORDER13667",
            "consignee": "LITTLE LAMB",
            "address1": "",
            "address2": "103 HAVENWOOD PLACE",
            "suburb": "BIRKENHEAD",
            "city": "NORTH SHORE CITY",
            "postcode": "0626",
            "country": "NZ",
            "delvref": "SSORDER13667",
            "delvinstructions": "A5SHEET X 1  A5 X 1",
            "contactname": "BROOKES STONE",
            "contactphone": "021 123456",
            "email": "info@littlelamb.co.nz",
            "isrural": null,
            "notrural": null,
            "costcentre": null,
            "status": {
                "Status": "DELIVERED",
                "ticketnumber": "SSPOT018162",
                "trackingurl": "http://gosweetspot.com/track/4180-SSPOT018162",
                "Picked": "2016-02-22T15:31:21",
                "Delivered": "2016-02-23T12:46:45",
                "manualticket": true
            },
            "products": [
                {
                    "productcode": "ABC",
                    "description": "WALL PAINT",
                    "units": 1,
                    "unitvalue": 10,
                    "countryofManufacture": "",
                    "unitkg": 1,
                    "imageurl": null,
                    "currency": "NZD",
                    "alreadySent": 0,
                    "fulfilledQty": 1,
                    "linetotal": 10
                }
            ]
        },
        {
            "packingslipno": "SSORDER13668",
            "consignee": "ROCK ON",
            "address1": "",
            "address2": "226 STEWART ROAD",
            "suburb": "RAMARAMA",
            "city": "AUCKLAND",
            "postcode": "2579",
            "country": "NZ",
            "delvref": "SSORDER13668",
            "delvinstructions": "A5 X 2  A4 X 5  OVERNIGHT X 2",
            "contactname": "ALBERT",
            "contactphone": "021212563",
            "email": "albert@rockon.co.nz",
            "isrural": null,
            "notrural": null,
            "costcentre": null,
            "status": {
                "Status": "DELIVERED",
                "ticketnumber": "SSPOT018161",
                "trackingurl": "http://gosweetspot.com/track/4180-SSPOT018161",
                "Picked": "2016-02-22T15:31:21",
                "Delivered": "2016-02-24T08:42:22",
                "manualticket": true
            },
            "products": [
                {
                    "productcode": "ABC",
                    "description": "WALL PAINT",
                    "units": 1,
                    "unitvalue": 10,
                    "countryofManufacture": "",
                    "unitkg": 1,
                    "imageurl": null,
                    "currency": "NZD",
                    "alreadySent": 0,
                    "fulfilledQty": 1,
                    "linetotal": 10
                }
            ]
        },
        {
            "packingslipno": "SSORDER13669",
            "consignee": "PREMIUM BLUE LTD",
            "address1": "5C",
            "address2": "102 ELLICE RD",
            "suburb": "GLENFIELD",
            "city": "NORTH SHORE CITY",
            "postcode": "0629",
            "country": "NZ",
            "delvref": "SSORDER13669",
            "delvinstructions": "A4 X 1  A2 X 1  OVERNIGHT X 1",
            "contactname": "ANDREW BURNS",
            "contactphone": "09 444 2131",
            "email": "andy@blueltd.co.nz",
            "isrural": null,
            "notrural": null,
            "costcentre": null,
            "status": {
                "Status": "DELIVERED",
                "ticketnumber": "SSPOT018160",
                "trackingurl": "http://gosweetspot.com/track/4180-SSPOT018160",
                "Picked": "2016-02-25T15:24:10",
                "Delivered": "2016-02-26T08:11:14",
                "manualticket": true
            },
            "products": [
                {
                    "productcode": "ABC",
                    "description": "WALL PAINT",
                    "units": 1,
                    "unitvalue": 10,
                    "countryofManufacture": "",
                    "unitkg": 1,
                    "imageurl": null,
                    "currency": "NZD",
                    "alreadySent": 0,
                    "fulfilledQty": 1,
                    "linetotal": 10
                }
            ]
        }
    ]
}
```