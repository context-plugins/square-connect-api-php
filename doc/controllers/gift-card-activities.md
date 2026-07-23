# Gift Card Activities

```php
$giftCardActivitiesController = $client->getGiftCardActivitiesController();
```

## Class Name

`GiftCardActivitiesController`

## Methods

* [List Gift Card Activities](../../doc/controllers/gift-card-activities.md#list-gift-card-activities)
* [Create Gift Card Activity](../../doc/controllers/gift-card-activities.md#create-gift-card-activity)


# List Gift Card Activities

Lists gift card activities. By default, you get gift card activities for all
gift cards in the seller's account. You can optionally specify query parameters to
filter the list. For example, you can get a list of gift card activities for a gift card,
for all gift cards in a specific region, or for activities within a time window.

```php
function listGiftCardActivities(
    ?string $giftCardId = null,
    ?string $type = null,
    ?string $locationId = null,
    ?string $beginTime = null,
    ?string $endTime = null,
    ?int $limit = null,
    ?string $cursor = null,
    ?string $sortOrder = null
): ListGiftCardActivitiesResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `giftCardId` | `?string` | Query, Optional | If you provide a gift card ID, the endpoint returns activities that belong<br>to the specified gift card. Otherwise, the endpoint returns all gift card activities for<br>the seller. |
| `type` | `?string` | Query, Optional | If you provide a type, the endpoint returns gift card activities of this type.<br>Otherwise, the endpoint returns all types of gift card activities. |
| `locationId` | `?string` | Query, Optional | If you provide a location ID, the endpoint returns gift card activities for that location.<br>Otherwise, the endpoint returns gift card activities for all locations. |
| `beginTime` | `?string` | Query, Optional | The timestamp for the beginning of the reporting period, in RFC 3339 format.<br>Inclusive. Default: The current time minus one year. |
| `endTime` | `?string` | Query, Optional | The timestamp for the end of the reporting period, in RFC 3339 format.<br>Inclusive. Default: The current time. |
| `limit` | `?int` | Query, Optional | If you provide a limit value, the endpoint returns the specified number<br>of results (or less) per page. A maximum value is 100. The default value is 50. |
| `cursor` | `?string` | Query, Optional | A pagination cursor returned by a previous call to this endpoint.<br>Provide this cursor to retrieve the next set of results for the original query.<br>If you do not provide the cursor, the call returns the first page of the results. |
| `sortOrder` | `?string` | Query, Optional | The order in which the endpoint returns the activities, based on `created_at`.<br><br>- `ASC` - Oldest to newest.<br>- `DESC` - Newest to oldest (default). |

## Requires scope

### oauth2

`GIFTCARDS_READ`

## Response Type

**200**: Success

[`ListGiftCardActivitiesResponse`](../../doc/models/list-gift-card-activities-response.md)

## Example Usage

```php
$giftCardActivitiesController = $client->getGiftCardActivitiesController();

try {
    $result = $giftCardActivitiesController->listGiftCardActivities();
    echo 'ListGiftCardActivitiesResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Create Gift Card Activity

Creates a gift card activity. For more information, see
[GiftCardActivity](https://developer.squareup.com/docs/gift-cards/using-gift-cards-api#giftcardactivity) and
[Using activated gift cards](https://developer.squareup.com/docs/gift-cards/using-gift-cards-api#using-activated-gift-cards).

```php
function createGiftCardActivity(CreateGiftCardActivityRequest $body): CreateGiftCardActivityResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreateGiftCardActivityRequest`](../../doc/models/create-gift-card-activity-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`GIFTCARDS_WRITE`

## Response Type

**200**: Success

[`CreateGiftCardActivityResponse`](../../doc/models/create-gift-card-activity-response.md)

## Example Usage

```php
$body = CreateGiftCardActivityRequestBuilder::init(
    GiftCardActivityBuilder::init(
        'location_id0',
        ApiHelper::deserialize('{"key1":"val1","key2":"val2"}')
    )->build(),
    'idempotency_key2'
)->build();

$giftCardActivitiesController = $client->getGiftCardActivitiesController();

try {
    $result = $giftCardActivitiesController->createGiftCardActivity($body);
    echo 'CreateGiftCardActivityResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

