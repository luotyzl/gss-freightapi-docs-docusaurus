# Customer Orders Model

| Attribute        | Type   | Description                                                                                                                             |
| ---------------- | ------ | --------------------------------------------------------------------------------------------------------------------------------------- |
| packingslipno    | string | unique order number or packing slip number from your system                                                                             |
| consignee        | string | receipient name                                                                                                                         |
| address1         | string | address line 2, street name                                                                                                             |
| suburb           | string | suburb name                                                                                                                             |
| city             | string | city name or state name. Depending on destination country, if state information is available, this should be the abbreviated state code |
| postcode         | string | post code, for NZ addresses, this can be left blank if unknown.                                                                         |
| country          | string | ISO Alpha 2 country code, eg NZ, AU, US, UK, CN                                                                                         |
| delvref          | string | Order number, or customer reference for this order.                                                                                     |
| delvinstructions | string | Any specific instructions to be printed on the label.                                                                                   |
| contactname      | string | name of person, optional.                                                                                                               |
| contactphone     | string | phone number of person, optional.                                                                                                       |
| email            | string | email address.                                                                                                                          |
| isrural          | string | is the address a rural delivery address                                                                                                 |
| notrural         | string | override and declared as not rural.                                                                                                     |
| costcentre       | string | cost centre to use.                                                                                                                     |
| status           | object | current status (Status Model)                                                                                                           |
| products         | object | array of line products on order [product model](/docs/models/product-model.md)                                                          |
