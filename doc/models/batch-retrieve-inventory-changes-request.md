
# Batch Retrieve Inventory Changes Request

## Structure

`BatchRetrieveInventoryChangesRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `catalogObjectIds` | `?(string[])` | Optional | The filter to return results by `CatalogObject` ID.<br>The filter is only applicable when set. The default value is null. | getCatalogObjectIds(): ?array | setCatalogObjectIds(?array catalogObjectIds): void |
| `cursor` | `?string` | Optional | A pagination cursor returned by a previous call to this endpoint.<br>Provide this to retrieve the next set of results for the original query.<br><br>See the [Pagination](https://developer.squareup.com/docs/working-with-apis/pagination) guide for more information. | getCursor(): ?string | setCursor(?string cursor): void |
| `locationIds` | `?(string[])` | Optional | The filter to return results by `Location` ID.<br>The filter is only applicable when set. The default value is null. | getLocationIds(): ?array | setLocationIds(?array locationIds): void |
| `states` | `?(string[])` | Optional | The filter to return `ADJUSTMENT` query results by<br>`InventoryState`. This filter is only applied when set.<br>The default value is null. | getStates(): ?array | setStates(?array states): void |
| `types` | `?(string[])` | Optional | The filter to return results by `InventoryChangeType` values other than `TRANSFER`.<br>The default value is `[PHYSICAL_COUNT, ADJUSTMENT]`. | getTypes(): ?array | setTypes(?array types): void |
| `updatedAfter` | `?string` | Optional | The filter to return results with their `calculated_at` value  <br>after the given time as specified in an RFC 3339 timestamp.<br>The default value is the UNIX epoch of (`1970-01-01T00:00:00Z`). | getUpdatedAfter(): ?string | setUpdatedAfter(?string updatedAfter): void |
| `updatedBefore` | `?string` | Optional | The filter to return results with their `created_at` or `calculated_at` value  <br>strictly before the given time as specified in an RFC 3339 timestamp.<br>The default value is the UNIX epoch of (`1970-01-01T00:00:00Z`). | getUpdatedBefore(): ?string | setUpdatedBefore(?string updatedBefore): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\BatchRetrieveInventoryChangesRequestBuilder;

$batchRetrieveInventoryChangesRequest = BatchRetrieveInventoryChangesRequestBuilder::init()
    ->catalogObjectIds(
        [
            'catalog_object_ids8'
        ]
    )
    ->cursor('cursor2')
    ->locationIds(
        [
            'location_ids4',
            'location_ids5',
            'location_ids6'
        ]
    )
    ->states(
        [
            'states8',
            'states9'
        ]
    )
    ->types(
        [
            'types3',
            'types4'
        ]
    )
    ->build();
```

