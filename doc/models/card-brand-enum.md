
# Card Brand Enum

Indicates a card's brand, such as `VISA` or `MASTERCARD`.

## Enumeration

`CardBrandEnum`

## Fields

| Name |
|  --- |
| `OTHER_BRAND` |
| `VISA` |
| `MASTERCARD` |
| `AMERICAN_EXPRESS` |
| `DISCOVER` |
| `DISCOVER_DINERS` |
| `JCB` |
| `CHINA_UNIONPAY` |
| `SQUARE_GIFT_CARD` |
| `SQUARE_CAPITAL_CARD` |
| `INTERAC` |
| `EFTPOS` |
| `FELICA` |
| `EBT` |

## Example

```php
use SquareConnectAPILib\Models\CardBrandEnum;

$cardBrand = CardBrandEnum::DISCOVER;
```

