
# Location Status Enum

The status of the location, whether a location is active or inactive.

## Enumeration

`LocationStatusEnum`

## Fields

| Name | Description |
|  --- | --- |
| `ACTIVE` | A location that is active for business. |
| `INACTIVE` | A location that is not active for business. Inactive locations just provide historical<br>information, so typically clients limit interaction with or hide these locations. |

## Example

```php
use SquareConnectAPILib\Models\LocationStatusEnum;

$locationStatus = LocationStatusEnum::ACTIVE;
```

