# Cards

```php
$cardsController = $client->getCardsController();
```

## Class Name

`CardsController`

## Methods

* [List Cards](../../doc/controllers/cards.md#list-cards)
* [Create Card](../../doc/controllers/cards.md#create-card)
* [Retrieve Card](../../doc/controllers/cards.md#retrieve-card)
* [Disable Card](../../doc/controllers/cards.md#disable-card)


# List Cards

Retrieves a list of cards owned by the account making the request.
A max of 25 cards will be returned.

```php
function listCards(
    ?string $cursor = null,
    ?string $customerId = null,
    ?bool $includeDisabled = null,
    ?string $referenceId = null,
    ?string $sortOrder = null
): ListCardsResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `cursor` | `?string` | Query, Optional | A pagination cursor returned by a previous call to this endpoint.<br>Provide this to retrieve the next set of results for your original query.<br><br>See [Pagination](https://developer.squareup.com/docs/basics/api101/pagination) for more information. |
| `customerId` | `?string` | Query, Optional | Limit results to cards associated with the customer supplied.<br>By default, all cards owned by the merchant are returned. |
| `includeDisabled` | `?bool` | Query, Optional | Includes disabled cards.<br>By default, all enabled cards owned by the merchant are returned. |
| `referenceId` | `?string` | Query, Optional | Limit results to cards associated with the reference_id supplied. |
| `sortOrder` | `?string` | Query, Optional | Sorts the returned list by when the card was created with the specified order.<br>This field defaults to ASC. |

## Requires scope

### oauth2

`PAYMENTS_READ`

## Response Type

**200**: Success

[`ListCardsResponse`](../../doc/models/list-cards-response.md)

## Example Usage

```php
$cardsController = $client->getCardsController();

try {
    $result = $cardsController->listCards();
    echo 'ListCardsResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Create Card

Adds a card on file to an existing merchant.

```php
function createCard(CreateCardRequest $body): CreateCardResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreateCardRequest`](../../doc/models/create-card-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`PAYMENTS_WRITE`

## Response Type

**200**: Success

[`CreateCardResponse`](../../doc/models/create-card-response.md)

## Example Usage

```php
$body = CreateCardRequestBuilder::init(
    CardBuilder::init()->build(),
    'idempotency_key2',
    'source_id0'
)->build();

$cardsController = $client->getCardsController();

try {
    $result = $cardsController->createCard($body);
    echo 'CreateCardResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Retrieve Card

Retrieves details for a specific Card.

```php
function retrieveCard(string $cardId): RetrieveCardResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `cardId` | `string` | Template, Required | Unique ID for the desired Card. |

## Requires scope

### oauth2

`PAYMENTS_READ`

## Response Type

**200**: Success

[`RetrieveCardResponse`](../../doc/models/retrieve-card-response.md)

## Example Usage

```php
$cardId = 'card_id4';

$cardsController = $client->getCardsController();

try {
    $result = $cardsController->retrieveCard($cardId);
    echo 'RetrieveCardResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Disable Card

Disables the card, preventing any further updates or charges.
Disabling an already disabled card is allowed but has no effect.

```php
function disableCard(string $cardId): DisableCardResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `cardId` | `string` | Template, Required | Unique ID for the desired Card. |

## Requires scope

### oauth2

`PAYMENTS_WRITE`

## Response Type

**200**: Success

[`DisableCardResponse`](../../doc/models/disable-card-response.md)

## Example Usage

```php
$cardId = 'card_id4';

$cardsController = $client->getCardsController();

try {
    $result = $cardsController->disableCard($cardId);
    echo 'DisableCardResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

