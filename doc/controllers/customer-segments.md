# Customer Segments

```php
$customerSegmentsController = $client->getCustomerSegmentsController();
```

## Class Name

`CustomerSegmentsController`

## Methods

* [List Customer Segments](../../doc/controllers/customer-segments.md#list-customer-segments)
* [Retrieve Customer Segment](../../doc/controllers/customer-segments.md#retrieve-customer-segment)


# List Customer Segments

Retrieves the list of customer segments of a business.

```php
function listCustomerSegments(?string $cursor = null, ?int $limit = null): ListCustomerSegmentsResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `cursor` | `?string` | Query, Optional | A pagination cursor returned by previous calls to `ListCustomerSegments`.<br>This cursor is used to retrieve the next set of query results.<br><br>For more information, see [Pagination](https://developer.squareup.com/docs/working-with-apis/pagination). |
| `limit` | `?int` | Query, Optional | The maximum number of results to return in a single page. This limit is advisory. The response might contain more or fewer results.<br>The limit is ignored if it is less than 1 or greater than 50. The default value is 50.<br><br>For more information, see [Pagination](https://developer.squareup.com/docs/working-with-apis/pagination). |

## Requires scope

### oauth2

`CUSTOMERS_READ`

## Response Type

**200**: Success

[`ListCustomerSegmentsResponse`](../../doc/models/list-customer-segments-response.md)

## Example Usage

```php
$customerSegmentsController = $client->getCustomerSegmentsController();

try {
    $result = $customerSegmentsController->listCustomerSegments();
    echo 'ListCustomerSegmentsResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Retrieve Customer Segment

Retrieves a specific customer segment as identified by the `segment_id` value.

```php
function retrieveCustomerSegment(string $segmentId): RetrieveCustomerSegmentResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `segmentId` | `string` | Template, Required | The Square-issued ID of the customer segment. |

## Requires scope

### oauth2

`CUSTOMERS_READ`

## Response Type

**200**: Success

[`RetrieveCustomerSegmentResponse`](../../doc/models/retrieve-customer-segment-response.md)

## Example Usage

```php
$segmentId = 'segment_id4';

$customerSegmentsController = $client->getCustomerSegmentsController();

try {
    $result = $customerSegmentsController->retrieveCustomerSegment($segmentId);
    echo 'RetrieveCustomerSegmentResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

