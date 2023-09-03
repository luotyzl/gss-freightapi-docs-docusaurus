# Customer Orders Package Model

| Attribute        | Type   | Description                                                                                                   |
| ---------------- | ------ | ------------------------------------------------------------------------------------------------------------- |
| PackageStockName | string | specify the name of the package here, e.g. GSS-A5 Satchel. The package needs to be previously configured here |
| Quantity         | int    | required                                                                                                      |
| WeightKg         | float  | Optional, if this is not present, will use the default weight of the package                                  |
| LengthCm         | float  | Optional, this parameter will be ignored if the package is a SATCHEL type                                     |
| WidthCm          | float  | Optional, this parameter will be ignored if the package is a SATCHEL type                                     |
| HeightCm         | float  | Optional, this parameter can be edited even if the package is a SATCHEL type                                  |
