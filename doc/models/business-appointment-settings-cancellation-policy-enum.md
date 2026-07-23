
# Business Appointment Settings Cancellation Policy Enum

The category of the seller’s cancellation policy.

## Enumeration

`BusinessAppointmentSettingsCancellationPolicyEnum`

## Fields

| Name | Description |
|  --- | --- |
| `CANCELLATION_TREATED_AS_NO_SHOW` | Cancellations are treated as no shows and may incur a fee as specified by `cancellation_fee_money`. |
| `CUSTOM_POLICY` | Cancellations follow the seller-specified policy that is described in free-form text and not enforced automatically by Square. |

## Example

```php
use SquareConnectAPILib\Models\BusinessAppointmentSettingsCancellationPolicyEnum;

$businessAppointmentSettingsCancellationPolicy = BusinessAppointmentSettingsCancellationPolicyEnum::CANCELLATION_TREATED_AS_NO_SHOW;
```

