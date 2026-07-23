# Gift Cards

```php
$giftCardsController = $client->getGiftCardsController();
```

## Class Name

`GiftCardsController`

## Methods

* [List Gift Cards](../../doc/controllers/gift-cards.md#list-gift-cards)
* [Create Gift Card](../../doc/controllers/gift-cards.md#create-gift-card)
* [Retrieve Gift Card from GAN](../../doc/controllers/gift-cards.md#retrieve-gift-card-from-gan)
* [Retrieve Gift Card from Nonce](../../doc/controllers/gift-cards.md#retrieve-gift-card-from-nonce)
* [Link Customer to Gift Card](../../doc/controllers/gift-cards.md#link-customer-to-gift-card)
* [Unlink Customer from Gift Card](../../doc/controllers/gift-cards.md#unlink-customer-from-gift-card)
* [Retrieve Gift Card](../../doc/controllers/gift-cards.md#retrieve-gift-card)


# List Gift Cards

Lists all gift cards. You can specify optional filters to retrieve
a subset of the gift cards.

```php
function listGiftCards(
    ?string $type = null,
    ?string $state = null,
    ?int $limit = null,
    ?string $cursor = null,
    ?string $customerId = null
): ListGiftCardsResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `type` | `?string` | Query, Optional | If a type is provided, gift cards of this type are returned<br>(see [GiftCardType](https://developer.squareup.com/reference/square_2021-08-18/enums/GiftCardType)).<br>If no type is provided, it returns gift cards of all types. |
| `state` | `?string` | Query, Optional | If the state is provided, it returns the gift cards in the specified state<br>(see [GiftCardStatus](https://developer.squareup.com/reference/square_2021-08-18/enums/GiftCardStatus)).<br>Otherwise, it returns the gift cards of all states. |
| `limit` | `?int` | Query, Optional | If a value is provided, it returns only that number of results per page.<br>The maximum number of results allowed per page is 50. The default value is 30. |
| `cursor` | `?string` | Query, Optional | A pagination cursor returned by a previous call to this endpoint.<br>Provide this cursor to retrieve the next set of results for the original query.<br>If a cursor is not provided, it returns the first page of the results.<br>For more information, see [Pagination](https://developer.squareup.com/docs/docs/working-with-apis/pagination). |
| `customerId` | `?string` | Query, Optional | If a value is provided, returns only the gift cards linked to the specified customer |

## Requires scope

### oauth2

`GIFTCARDS_READ`

## Response Type

**200**: Success

[`ListGiftCardsResponse`](../../doc/models/list-gift-cards-response.md)

## Example Usage

```php
$giftCardsController = $client->getGiftCardsController();

try {
    $result = $giftCardsController->listGiftCards();
    echo 'ListGiftCardsResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Create Gift Card

Creates a digital gift card or registers a physical (plastic) gift card. You must activate the gift card before
it can be used for payment. For more information, see
[Selling gift cards](https://developer.squareup.com/docs/gift-cards/using-gift-cards-api#selling-square-gift-cards).

```php
function createGiftCard(CreateGiftCardRequest $body): CreateGiftCardResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreateGiftCardRequest`](../../doc/models/create-gift-card-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`GIFTCARDS_WRITE`

## Response Type

**200**: Success

[`CreateGiftCardResponse`](../../doc/models/create-gift-card-response.md)

## Example Usage

```php
$body = CreateGiftCardRequestBuilder::init(
    GiftCardBuilder::init(
        ApiHelper::deserialize('{"key1":"val1","key2":"val2"}')
    )->build(),
    'idempotency_key2',
    'location_id0'
)->build();

$giftCardsController = $client->getGiftCardsController();

try {
    $result = $giftCardsController->createGiftCard($body);
    echo 'CreateGiftCardResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Retrieve Gift Card from GAN

Retrieves a gift card using the gift card account number (GAN).

```php
function retrieveGiftCardFromGAN(RetrieveGiftCardFromGANRequest $body): RetrieveGiftCardFromGANResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`RetrieveGiftCardFromGANRequest`](../../doc/models/retrieve-gift-card-from-gan-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`GIFTCARDS_READ`

## Response Type

**200**: Success

[`RetrieveGiftCardFromGANResponse`](../../doc/models/retrieve-gift-card-from-gan-response.md)

## Example Usage

```php
$body = RetrieveGiftCardFromGANRequestBuilder::init(
    'gan2'
)->build();

$giftCardsController = $client->getGiftCardsController();

try {
    $result = $giftCardsController->retrieveGiftCardFromGAN($body);
    echo 'RetrieveGiftCardFromGANResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Retrieve Gift Card from Nonce

Retrieves a gift card using a nonce (a secure token) that represents the gift card.

```php
function retrieveGiftCardFromNonce(RetrieveGiftCardFromNonceRequest $body): RetrieveGiftCardFromNonceResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`RetrieveGiftCardFromNonceRequest`](../../doc/models/retrieve-gift-card-from-nonce-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`GIFTCARDS_READ`

## Response Type

**200**: Success

[`RetrieveGiftCardFromNonceResponse`](../../doc/models/retrieve-gift-card-from-nonce-response.md)

## Example Usage

```php
$body = RetrieveGiftCardFromNonceRequestBuilder::init(
    'nonce8'
)->build();

$giftCardsController = $client->getGiftCardsController();

try {
    $result = $giftCardsController->retrieveGiftCardFromNonce($body);
    echo 'RetrieveGiftCardFromNonceResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Link Customer to Gift Card

Links a customer to a gift card

```php
function linkCustomerToGiftCard(
    string $giftCardId,
    LinkCustomerToGiftCardRequest $body
): LinkCustomerToGiftCardResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `giftCardId` | `string` | Template, Required | The ID of the gift card to link. |
| `body` | [`LinkCustomerToGiftCardRequest`](../../doc/models/link-customer-to-gift-card-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`GIFTCARDS_WRITE`

## Response Type

**200**: Success

[`LinkCustomerToGiftCardResponse`](../../doc/models/link-customer-to-gift-card-response.md)

## Example Usage

```php
$giftCardId = 'gift_card_id8';

$body = LinkCustomerToGiftCardRequestBuilder::init(
    'customer_id4'
)->build();

$giftCardsController = $client->getGiftCardsController();

try {
    $result = $giftCardsController->linkCustomerToGiftCard(
        $giftCardId,
        $body
    );
    echo 'LinkCustomerToGiftCardResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Unlink Customer from Gift Card

Unlinks a customer from a gift card

```php
function unlinkCustomerFromGiftCard(
    string $giftCardId,
    UnlinkCustomerFromGiftCardRequest $body
): UnlinkCustomerFromGiftCardResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `giftCardId` | `string` | Template, Required | - |
| `body` | [`UnlinkCustomerFromGiftCardRequest`](../../doc/models/unlink-customer-from-gift-card-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`GIFTCARDS_WRITE`

## Response Type

**200**: Success

[`UnlinkCustomerFromGiftCardResponse`](../../doc/models/unlink-customer-from-gift-card-response.md)

## Example Usage

```php
$giftCardId = 'gift_card_id8';

$body = UnlinkCustomerFromGiftCardRequestBuilder::init(
    'customer_id4'
)->build();

$giftCardsController = $client->getGiftCardsController();

try {
    $result = $giftCardsController->unlinkCustomerFromGiftCard(
        $giftCardId,
        $body
    );
    echo 'UnlinkCustomerFromGiftCardResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Retrieve Gift Card

Retrieves a gift card using its ID.

```php
function retrieveGiftCard(string $id): RetrieveGiftCardResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of the gift card to retrieve. |

## Requires scope

### oauth2

`GIFTCARDS_READ`

## Response Type

**200**: Success

[`RetrieveGiftCardResponse`](../../doc/models/retrieve-gift-card-response.md)

## Example Usage

```php
$id = 'id0';

$giftCardsController = $client->getGiftCardsController();

try {
    $result = $giftCardsController->retrieveGiftCard($id);
    echo 'RetrieveGiftCardResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

