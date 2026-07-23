
# Batch Retrieve Inventory Counts Response

## Structure

`BatchRetrieveInventoryCountsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `counts` | [`?(InventoryCount[])`](../../doc/models/inventory-count.md) | Optional | The current calculated inventory counts for the requested objects<br>and locations. | getCounts(): ?array | setCounts(?array counts): void |
| `cursor` | `?string` | Optional | The pagination cursor to be used in a subsequent request. If unset,<br>this is the final response.<br><br>See the [Pagination](https://developer.squareup.com/docs/working-with-apis/pagination) guide for more information. | getCursor(): ?string | setCursor(?string cursor): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\BatchRetrieveInventoryCountsResponseBuilder;
use SquareConnectAPILib\Models\Builders\InventoryCountBuilder;

$batchRetrieveInventoryCountsResponse = BatchRetrieveInventoryCountsResponseBuilder::init()
    ->counts(
        [
            InventoryCountBuilder::init()
                ->calculatedAt('2016-11-16T22:28:01.223Z')
                ->catalogObjectId('W62UWFY35CWMYGVWK6TWJDNI')
                ->catalogObjectType('ITEM_VARIATION')
                ->isEstimated(false)
                ->locationId('59TNP9SA8VGDA')
                ->quantity('79')
                ->state('IN_STOCK')
                ->build()
        ]
    )
    ->cursor('cursor4')
    ->errors(
        []
    )
    ->build();
```

