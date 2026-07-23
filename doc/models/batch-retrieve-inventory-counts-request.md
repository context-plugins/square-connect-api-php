
# Batch Retrieve Inventory Counts Request

## Structure

`BatchRetrieveInventoryCountsRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `catalogObjectIds` | `?(string[])` | Optional | The filter to return results by `CatalogObject` ID.<br>The filter is applicable only when set.  The default is null. | getCatalogObjectIds(): ?array | setCatalogObjectIds(?array catalogObjectIds): void |
| `cursor` | `?string` | Optional | A pagination cursor returned by a previous call to this endpoint.<br>Provide this to retrieve the next set of results for the original query.<br><br>See the [Pagination](https://developer.squareup.com/docs/working-with-apis/pagination) guide for more information. | getCursor(): ?string | setCursor(?string cursor): void |
| `locationIds` | `?(string[])` | Optional | The filter to return results by `Location` ID.<br>This filter is applicable only when set. The default is null. | getLocationIds(): ?array | setLocationIds(?array locationIds): void |
| `states` | `?(string[])` | Optional | The filter to return results by `InventoryState`. The filter is only applicable when set.<br>Ignored are untracked states of `NONE`, `SOLD`, and `UNLINKED_RETURN`.<br>The default is null. | getStates(): ?array | setStates(?array states): void |
| `updatedAfter` | `?string` | Optional | The filter to return results with their `calculated_at` value<br>after the given time as specified in an RFC 3339 timestamp.<br>The default value is the UNIX epoch of (`1970-01-01T00:00:00Z`). | getUpdatedAfter(): ?string | setUpdatedAfter(?string updatedAfter): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\BatchRetrieveInventoryCountsRequestBuilder;

$batchRetrieveInventoryCountsRequest = BatchRetrieveInventoryCountsRequestBuilder::init()
    ->catalogObjectIds(
        [
            'catalog_object_ids8',
            'catalog_object_ids9',
            'catalog_object_ids0'
        ]
    )
    ->cursor('cursor2')
    ->locationIds(
        [
            'location_ids4'
        ]
    )
    ->states(
        [
            'states2',
            'states1'
        ]
    )
    ->updatedAfter('updated_after0')
    ->build();
```

