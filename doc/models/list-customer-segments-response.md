
# List Customer Segments Response

Defines the fields that are included in the response body for requests to the `ListCustomerSegments` endpoint.

Either `errors` or `segments` is present in a given response (never both).

## Structure

`ListCustomerSegmentsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | A pagination cursor to be used in subsequent calls to `ListCustomerSegments`<br>to retrieve the next set of query results. The cursor is only present if the request succeeded and<br>additional results are available.<br><br>For more information, see [Pagination](https://developer.squareup.com/docs/working-with-apis/pagination). | getCursor(): ?string | setCursor(?string cursor): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `segments` | [`?(CustomerSegment[])`](../../doc/models/customer-segment.md) | Optional | The list of customer segments belonging to the associated Square account. | getSegments(): ?array | setSegments(?array segments): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ListCustomerSegmentsResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\CustomerSegmentBuilder;

$listCustomerSegmentsResponse = ListCustomerSegmentsResponseBuilder::init()
    ->cursor('cursor0')
    ->errors(
        [
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build(),
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build(),
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build()
        ]
    )
    ->segments(
        [
            CustomerSegmentBuilder::init(
                'Lapsed'
            )
                ->createdAt('2020-01-09T19:33:24.469Z')
                ->id('GMNXRZVEXNQDF.CHURN_RISK')
                ->updatedAt('2020-04-13T21:47:04Z')
                ->build(),
            CustomerSegmentBuilder::init(
                'Regulars'
            )
                ->createdAt('2020-01-09T19:33:24.486Z')
                ->id('GMNXRZVEXNQDF.LOYAL')
                ->updatedAt('2020-04-13T21:47:04Z')
                ->build(),
            CustomerSegmentBuilder::init(
                'Reachable'
            )
                ->createdAt('2020-01-09T19:33:21.813Z')
                ->id('GMNXRZVEXNQDF.REACHABLE')
                ->updatedAt('2020-04-13T21:47:04Z')
                ->build(),
            CustomerSegmentBuilder::init(
                'Instant Profile'
            )
                ->createdAt('2020-01-09T19:33:25Z')
                ->id('gv2:KF92J19VXN5FK30GX2E8HSGQ20')
                ->updatedAt('2020-04-13T23:01:03Z')
                ->build()
        ]
    )
    ->build();
```

