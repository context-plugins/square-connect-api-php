
# List Cards Request

Retrieves details for a specific Card. Accessible via
HTTP requests at GET https://connect.squareup.com/v2/cards

## Structure

`ListCardsRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | A pagination cursor returned by a previous call to this endpoint.<br>Provide this to retrieve the next set of results for your original query.<br><br>See [Pagination](https://developer.squareup.com/docs/basics/api101/pagination) for more information.<br><br>**Constraints**: *Maximum Length*: `256` | getCursor(): ?string | setCursor(?string cursor): void |
| `customerId` | `?string` | Optional | Limit results to cards associated with the customer supplied.<br>By default, all cards owned by the merchant are returned. | getCustomerId(): ?string | setCustomerId(?string customerId): void |
| `includeDisabled` | `?bool` | Optional | Includes disabled cards.<br>By default, all enabled cards owned by the merchant are returned. | getIncludeDisabled(): ?bool | setIncludeDisabled(?bool includeDisabled): void |
| `referenceId` | `?string` | Optional | Limit results to cards associated with the reference_id supplied. | getReferenceId(): ?string | setReferenceId(?string referenceId): void |
| `sortOrder` | `?string` | Optional | Sorts the returned list by when the card was created with the specified order.<br>This field defaults to ASC. | getSortOrder(): ?string | setSortOrder(?string sortOrder): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ListCardsRequestBuilder;

$listCardsRequest = ListCardsRequestBuilder::init()
    ->cursor('cursor4')
    ->customerId('customer_id8')
    ->includeDisabled(false)
    ->referenceId('reference_id8')
    ->sortOrder('sort_order0')
    ->build();
```

