
# Tender Card Details Status Enum

Indicates the card transaction's current status.

## Enumeration

`TenderCardDetailsStatusEnum`

## Fields

| Name | Description |
|  --- | --- |
| `AUTHORIZED` | The card transaction has been authorized but not yet captured. |
| `CAPTURED` | The card transaction was authorized and subsequently captured (i.e., completed). |
| `VOIDED` | The card transaction was authorized and subsequently voided (i.e., canceled). |
| `FAILED` | The card transaction failed. |

## Example

```php
use SquareConnectAPILib\Models\TenderCardDetailsStatusEnum;

$tenderCardDetailsStatus = TenderCardDetailsStatusEnum::AUTHORIZED;
```

