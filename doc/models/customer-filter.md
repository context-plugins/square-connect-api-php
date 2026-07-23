
# Customer Filter

Represents a set of `CustomerQuery` filters used to limit the set of
customers returned by the [SearchCustomers](https://developer.squareup.com/reference/square_2021-08-18/customers-api/search-customers) endpoint.

## Structure

`CustomerFilter`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `createdAt` | [`?TimeRange`](../../doc/models/time-range.md) | Optional | Represents a generic time range. The start and end values are<br>represented in RFC 3339 format. Time ranges are customized to be<br>inclusive or exclusive based on the needs of a particular endpoint.<br>Refer to the relevant endpoint-specific documentation to determine<br>how time ranges are handled. | getCreatedAt(): ?TimeRange | setCreatedAt(?TimeRange createdAt): void |
| `creationSource` | [`?CustomerCreationSourceFilter`](../../doc/models/customer-creation-source-filter.md) | Optional | The creation source filter.<br><br>If one or more creation sources are set, customer profiles are included in,<br>or excluded from, the result if they match at least one of the filter criteria. | getCreationSource(): ?CustomerCreationSourceFilter | setCreationSource(?CustomerCreationSourceFilter creationSource): void |
| `emailAddress` | [`?CustomerTextFilter`](../../doc/models/customer-text-filter.md) | Optional | A filter to select customers based on exact or fuzzy matching of<br>customer attributes against a specified query. Depending on the customer attributes,<br>the filter can be case-sensitive. This filter can be exact or fuzzy, but it cannot be both. | getEmailAddress(): ?CustomerTextFilter | setEmailAddress(?CustomerTextFilter emailAddress): void |
| `groupIds` | [`?FilterValue`](../../doc/models/filter-value.md) | Optional | A filter to select resources based on an exact field value. For any given<br>value, the value can only be in one property. Depending on the field, either<br>all properties can be set or only a subset will be available.<br><br>Refer to the documentation of the field. | getGroupIds(): ?FilterValue | setGroupIds(?FilterValue groupIds): void |
| `phoneNumber` | [`?CustomerTextFilter`](../../doc/models/customer-text-filter.md) | Optional | A filter to select customers based on exact or fuzzy matching of<br>customer attributes against a specified query. Depending on the customer attributes,<br>the filter can be case-sensitive. This filter can be exact or fuzzy, but it cannot be both. | getPhoneNumber(): ?CustomerTextFilter | setPhoneNumber(?CustomerTextFilter phoneNumber): void |
| `referenceId` | [`?CustomerTextFilter`](../../doc/models/customer-text-filter.md) | Optional | A filter to select customers based on exact or fuzzy matching of<br>customer attributes against a specified query. Depending on the customer attributes,<br>the filter can be case-sensitive. This filter can be exact or fuzzy, but it cannot be both. | getReferenceId(): ?CustomerTextFilter | setReferenceId(?CustomerTextFilter referenceId): void |
| `updatedAt` | [`?TimeRange`](../../doc/models/time-range.md) | Optional | Represents a generic time range. The start and end values are<br>represented in RFC 3339 format. Time ranges are customized to be<br>inclusive or exclusive based on the needs of a particular endpoint.<br>Refer to the relevant endpoint-specific documentation to determine<br>how time ranges are handled. | getUpdatedAt(): ?TimeRange | setUpdatedAt(?TimeRange updatedAt): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CustomerFilterBuilder;
use SquareConnectAPILib\Models\Builders\TimeRangeBuilder;
use SquareConnectAPILib\Models\Builders\CustomerCreationSourceFilterBuilder;
use SquareConnectAPILib\Models\Builders\CustomerTextFilterBuilder;
use SquareConnectAPILib\Models\Builders\FilterValueBuilder;

$customerFilter = CustomerFilterBuilder::init()
    ->createdAt(
        TimeRangeBuilder::init()
            ->endAt('end_at8')
            ->startAt('start_at4')
            ->build()
    )
    ->creationSource(
        CustomerCreationSourceFilterBuilder::init()
            ->rule('rule6')
            ->values(
                [
                    'values6',
                    'values5',
                    'values4'
                ]
            )
            ->build()
    )
    ->emailAddress(
        CustomerTextFilterBuilder::init()
            ->exact('exact2')
            ->fuzzy('fuzzy8')
            ->build()
    )
    ->groupIds(
        FilterValueBuilder::init()
            ->all(
                [
                    'all5',
                    'all4',
                    'all3'
                ]
            )
            ->any(
                [
                    'any2',
                    'any3',
                    'any4'
                ]
            )
            ->none(
                [
                    'none7',
                    'none8'
                ]
            )
            ->build()
    )
    ->phoneNumber(
        CustomerTextFilterBuilder::init()
            ->exact('exact2')
            ->fuzzy('fuzzy8')
            ->build()
    )
    ->build();
```

