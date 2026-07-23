
# Business Appointment Settings

The service appointment settings, including where and how the service is provided.

## Structure

`BusinessAppointmentSettings`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `alignmentTime` | `?string` | Optional | The time unit of the service duration for bookings. | getAlignmentTime(): ?string | setAlignmentTime(?string alignmentTime): void |
| `anyTeamMemberBookingEnabled` | `?bool` | Optional | Indicates whether a customer can choose from all available time slots and have a staff member assigned<br>automatically (`true`) or not (`false`). | getAnyTeamMemberBookingEnabled(): ?bool | setAnyTeamMemberBookingEnabled(?bool anyTeamMemberBookingEnabled): void |
| `cancellationFeeMoney` | [`?Money`](../../doc/models/money.md) | Optional | Represents an amount of money. `Money` fields can be signed or unsigned.<br>Fields that do not explicitly define whether they are signed or unsigned are<br>considered unsigned and can only hold positive amounts. For signed fields, the<br>sign of the value indicates the purpose of the money transfer. See<br>[Working with Monetary Amounts](https://developer.squareup.com/docs/build-basics/working-with-monetary-amounts)<br>for more information. | getCancellationFeeMoney(): ?Money | setCancellationFeeMoney(?Money cancellationFeeMoney): void |
| `cancellationPolicy` | `?string` | Optional | The cancellation policy adopted by the seller. | getCancellationPolicy(): ?string | setCancellationPolicy(?string cancellationPolicy): void |
| `cancellationPolicyText` | `?string` | Optional | The free-form text of the seller's cancellation policy. | getCancellationPolicyText(): ?string | setCancellationPolicyText(?string cancellationPolicyText): void |
| `cancellationWindowSeconds` | `?int` | Optional | The cut-off time in seconds for allowing clients to cancel or reschedule an appointment. | getCancellationWindowSeconds(): ?int | setCancellationWindowSeconds(?int cancellationWindowSeconds): void |
| `locationTypes` | `?(string[])` | Optional | Types of the location allowed for bookings. | getLocationTypes(): ?array | setLocationTypes(?array locationTypes): void |
| `maxAppointmentsPerDayLimit` | `?int` | Optional | The maximum number of daily appointments per team member or per location. | getMaxAppointmentsPerDayLimit(): ?int | setMaxAppointmentsPerDayLimit(?int maxAppointmentsPerDayLimit): void |
| `maxAppointmentsPerDayLimitType` | `?string` | Optional | Indicates whether the daily appointment limit applies to team members or to<br>business locations. | getMaxAppointmentsPerDayLimitType(): ?string | setMaxAppointmentsPerDayLimitType(?string maxAppointmentsPerDayLimitType): void |
| `maxBookingLeadTimeSeconds` | `?int` | Optional | The maximum lead time in seconds before a service can be booked. Bookings must be created at most this far ahead of the booking's starting time. | getMaxBookingLeadTimeSeconds(): ?int | setMaxBookingLeadTimeSeconds(?int maxBookingLeadTimeSeconds): void |
| `minBookingLeadTimeSeconds` | `?int` | Optional | The minimum lead time in seconds before a service can be booked. Bookings must be created at least this far ahead of the booking's starting time. | getMinBookingLeadTimeSeconds(): ?int | setMinBookingLeadTimeSeconds(?int minBookingLeadTimeSeconds): void |
| `multipleServiceBookingEnabled` | `?bool` | Optional | Indicates whether a customer can book multiple services in a single online booking. | getMultipleServiceBookingEnabled(): ?bool | setMultipleServiceBookingEnabled(?bool multipleServiceBookingEnabled): void |
| `skipBookingFlowStaffSelection` | `?bool` | Optional | Indicates whether customers has an assigned staff member (`true`) or can select s staff member of their choice (`false`). | getSkipBookingFlowStaffSelection(): ?bool | setSkipBookingFlowStaffSelection(?bool skipBookingFlowStaffSelection): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\BusinessAppointmentSettingsBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$businessAppointmentSettings = BusinessAppointmentSettingsBuilder::init()
    ->alignmentTime('alignment_time8')
    ->anyTeamMemberBookingEnabled(false)
    ->cancellationFeeMoney(
        MoneyBuilder::init()
            ->amount(72)
            ->currency('currency8')
            ->build()
    )
    ->cancellationPolicy('cancellation_policy4')
    ->cancellationPolicyText('cancellation_policy_text0')
    ->build();
```

