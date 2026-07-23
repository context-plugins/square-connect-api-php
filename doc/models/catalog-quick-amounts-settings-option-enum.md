
# Catalog Quick Amounts Settings Option Enum

Determines a seller's option on Quick Amounts feature.

## Enumeration

`CatalogQuickAmountsSettingsOptionEnum`

## Fields

| Name | Description |
|  --- | --- |
| `DISABLED` | Option for seller to disable Quick Amounts. |
| `MANUAL` | Option for seller to choose manually created Quick Amounts. |
| `AUTO` | Option for seller to choose automatically created Quick Amounts. |

## Example

```php
use SquareConnectAPILib\Models\CatalogQuickAmountsSettingsOptionEnum;

$catalogQuickAmountsSettingsOption = CatalogQuickAmountsSettingsOptionEnum::AUTO;
```

