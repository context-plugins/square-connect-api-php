
# Merchant Status Enum

## Enumeration

`MerchantStatusEnum`

## Fields

| Name | Description |
|  --- | --- |
| `ACTIVE` | A fully operational merchant account. The merchant can interact with Square products and APIs. |
| `INACTIVE` | A functionally limited merchant account. The merchant can only have limited interaction<br>via Square APIs. The merchant cannot access the seller dashboard. |

## Example

```php
use SquareConnectAPILib\Models\MerchantStatusEnum;

$merchantStatus = MerchantStatusEnum::ACTIVE;
```

