
# Retrieve Customer Segment Response

Defines the fields that are included in the response body for requests to the `RetrieveCustomerSegment` endpoint.

Either `errors` or `segment` is present in a given response (never both).

## Structure

`RetrieveCustomerSegmentResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `segment` | [`?CustomerSegment`](../../doc/models/customer-segment.md) | Optional | Represents a group of customer profiles that match one or more predefined filter criteria.<br><br>Segments (also known as Smart Groups) are defined and created within the Customer Directory in the<br>Square Seller Dashboard or Point of Sale. | getSegment(): ?CustomerSegment | setSegment(?CustomerSegment segment): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\RetrieveCustomerSegmentResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\CustomerSegmentBuilder;

$retrieveCustomerSegmentResponse = RetrieveCustomerSegmentResponseBuilder::init()
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
                ->build()
        ]
    )
    ->segment(
        CustomerSegmentBuilder::init(
            'Lapsed'
        )
            ->createdAt('2020-01-09T19:33:24.469Z')
            ->id('GMNXRZVEXNQDF.CHURN_RISK')
            ->updatedAt('2020-04-13T23:01:13Z')
            ->build()
    )
    ->build();
```

