# Product Model

| Attribute            | Type    | Description                                     |
|----------------------|---------|-------------------------------------------------|
| productcode          | string  | SKU of Product                                  |
| description          | string  | Name of Product                                 |
| units                | integer | Units ordered                                   |
| unitvalue            | decimal | Value per unit                                  |
| countryofManufacture | string  | ISO Alpha 2 country code, eg NZ, AU, US, UK, CN |
| imageurl             | string  | An image of the product                         |
| currency             | string  | 3 letter code for currency                      |
| alreadySent          | integer | Amount of product fulfilled prior to this order |
| fulfilledQty         | integer | mount of product fulfilled on this order        |
| linetotal            | decimal | Total value of this order                       |
