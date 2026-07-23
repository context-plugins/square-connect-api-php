
# Segment Filter

A query filter to search for appointment segments by.

## Structure

`SegmentFilter`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `serviceVariationId` | `string` | Required | The ID of the [CatalogItemVariation](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogItemVariation) representing the service booked in this segment.<br><br>**Constraints**: *Minimum Length*: `1` | getServiceVariationId(): string | setServiceVariationId(string serviceVariationId): void |
| `teamMemberIdFilter` | [`?FilterValue`](../../doc/models/filter-value.md) | Optional | A filter to select resources based on an exact field value. For any given<br>value, the value can only be in one property. Depending on the field, either<br>all properties can be set or only a subset will be available.<br><br>Refer to the documentation of the field. | getTeamMemberIdFilter(): ?FilterValue | setTeamMemberIdFilter(?FilterValue teamMemberIdFilter): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SegmentFilterBuilder;
use SquareConnectAPILib\Models\Builders\FilterValueBuilder;

$segmentFilter = SegmentFilterBuilder::init(
    'service_variation_id0'
)
    ->teamMemberIdFilter(
        FilterValueBuilder::init()
            ->all(
                [
                    'all5',
                    'all6',
                    'all7'
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
    ->build();
```

