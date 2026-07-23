# Loyalty

```php
$loyaltyController = $client->getLoyaltyController();
```

## Class Name

`LoyaltyController`

## Methods

* [Create Loyalty Account](../../doc/controllers/loyalty.md#create-loyalty-account)
* [Search Loyalty Accounts](../../doc/controllers/loyalty.md#search-loyalty-accounts)
* [Retrieve Loyalty Account](../../doc/controllers/loyalty.md#retrieve-loyalty-account)
* [Accumulate Loyalty Points](../../doc/controllers/loyalty.md#accumulate-loyalty-points)
* [Adjust Loyalty Points](../../doc/controllers/loyalty.md#adjust-loyalty-points)
* [Search Loyalty Events](../../doc/controllers/loyalty.md#search-loyalty-events)
* [List Loyalty Programs](../../doc/controllers/loyalty.md#list-loyalty-programs)
* [Retrieve Loyalty Program](../../doc/controllers/loyalty.md#retrieve-loyalty-program)
* [Calculate Loyalty Points](../../doc/controllers/loyalty.md#calculate-loyalty-points)
* [Create Loyalty Reward](../../doc/controllers/loyalty.md#create-loyalty-reward)
* [Search Loyalty Rewards](../../doc/controllers/loyalty.md#search-loyalty-rewards)
* [Delete Loyalty Reward](../../doc/controllers/loyalty.md#delete-loyalty-reward)
* [Retrieve Loyalty Reward](../../doc/controllers/loyalty.md#retrieve-loyalty-reward)
* [Redeem Loyalty Reward](../../doc/controllers/loyalty.md#redeem-loyalty-reward)


# Create Loyalty Account

Creates a loyalty account. To create a loyalty account, you must provide the `program_id` and a `mapping` with the `phone_number` of the buyer.

```php
function createLoyaltyAccount(CreateLoyaltyAccountRequest $body): CreateLoyaltyAccountResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreateLoyaltyAccountRequest`](../../doc/models/create-loyalty-account-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`LOYALTY_WRITE`

## Response Type

**200**: Success

[`CreateLoyaltyAccountResponse`](../../doc/models/create-loyalty-account-response.md)

## Example Usage

```php
$body = CreateLoyaltyAccountRequestBuilder::init(
    'idempotency_key2',
    LoyaltyAccountBuilder::init(
        'program_id6'
    )->build()
)->build();

$loyaltyController = $client->getLoyaltyController();

try {
    $result = $loyaltyController->createLoyaltyAccount($body);
    echo 'CreateLoyaltyAccountResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Search Loyalty Accounts

Searches for loyalty accounts in a loyalty program.

You can search for a loyalty account using the phone number or customer ID associated with the account. To return all loyalty accounts, specify an empty `query` object or omit it entirely.

Search results are sorted by `created_at` in ascending order.

```php
function searchLoyaltyAccounts(SearchLoyaltyAccountsRequest $body): SearchLoyaltyAccountsResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`SearchLoyaltyAccountsRequest`](../../doc/models/search-loyalty-accounts-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`LOYALTY_READ`

## Response Type

**200**: Success

[`SearchLoyaltyAccountsResponse`](../../doc/models/search-loyalty-accounts-response.md)

## Example Usage

```php
$body = SearchLoyaltyAccountsRequestBuilder::init()->build();

$loyaltyController = $client->getLoyaltyController();

try {
    $result = $loyaltyController->searchLoyaltyAccounts($body);
    echo 'SearchLoyaltyAccountsResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Retrieve Loyalty Account

Retrieves a loyalty account.

```php
function retrieveLoyaltyAccount(string $accountId): RetrieveLoyaltyAccountResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `accountId` | `string` | Template, Required | The ID of the [loyalty account](https://developer.squareup.com/reference/square_2021-08-18/objects/LoyaltyAccount) to retrieve. |

## Requires scope

### oauth2

`LOYALTY_READ`

## Response Type

**200**: Success

[`RetrieveLoyaltyAccountResponse`](../../doc/models/retrieve-loyalty-account-response.md)

## Example Usage

```php
$accountId = 'account_id2';

$loyaltyController = $client->getLoyaltyController();

try {
    $result = $loyaltyController->retrieveLoyaltyAccount($accountId);
    echo 'RetrieveLoyaltyAccountResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Accumulate Loyalty Points

Adds points to a loyalty account.

- If you are using the Orders API to manage orders, you only provide the `order_id`.
  The endpoint reads the order to compute points to add to the buyer's account.
- If you are not using the Orders API to manage orders,
  you first perform a client-side computation to compute the points.  
  For spend-based and visit-based programs, you can first call
  [CalculateLoyaltyPoints](https://developer.squareup.com/reference/square_2021-08-18/loyalty-api/calculate-loyalty-points) to compute the points  
  that you provide to this endpoint.

__Note:__ The country of the seller's Square account determines whether tax is included in the purchase amount when accruing points for spend-based and visit-based programs.
For more information, see [Availability of Square Loyalty](https://developer.squareup.com/docs/loyalty-api/overview#loyalty-market-availability).

```php
function accumulateLoyaltyPoints(
    string $accountId,
    AccumulateLoyaltyPointsRequest $body
): AccumulateLoyaltyPointsResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `accountId` | `string` | Template, Required | The [loyalty account](https://developer.squareup.com/reference/square_2021-08-18/objects/LoyaltyAccount) ID to which to add the points. |
| `body` | [`AccumulateLoyaltyPointsRequest`](../../doc/models/accumulate-loyalty-points-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`LOYALTY_WRITE`

## Response Type

**200**: Success

[`AccumulateLoyaltyPointsResponse`](../../doc/models/accumulate-loyalty-points-response.md)

## Example Usage

```php
$accountId = 'account_id2';

$body = AccumulateLoyaltyPointsRequestBuilder::init(
    LoyaltyEventAccumulatePointsBuilder::init()->build(),
    'idempotency_key2',
    'location_id0'
)->build();

$loyaltyController = $client->getLoyaltyController();

try {
    $result = $loyaltyController->accumulateLoyaltyPoints(
        $accountId,
        $body
    );
    echo 'AccumulateLoyaltyPointsResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Adjust Loyalty Points

Adds points to or subtracts points from a buyer's account.

Use this endpoint only when you need to manually adjust points. Otherwise, in your application flow, you call
[AccumulateLoyaltyPoints](https://developer.squareup.com/reference/square_2021-08-18/loyalty-api/accumulate-loyalty-points)
to add points when a buyer pays for the purchase.

```php
function adjustLoyaltyPoints(string $accountId, AdjustLoyaltyPointsRequest $body): AdjustLoyaltyPointsResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `accountId` | `string` | Template, Required | The ID of the [loyalty account](https://developer.squareup.com/reference/square_2021-08-18/objects/LoyaltyAccount) in which to adjust the points. |
| `body` | [`AdjustLoyaltyPointsRequest`](../../doc/models/adjust-loyalty-points-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`LOYALTY_WRITE`

## Response Type

**200**: Success

[`AdjustLoyaltyPointsResponse`](../../doc/models/adjust-loyalty-points-response.md)

## Example Usage

```php
$accountId = 'account_id2';

$body = AdjustLoyaltyPointsRequestBuilder::init(
    LoyaltyEventAdjustPointsBuilder::init(
        96
    )->build(),
    'idempotency_key2'
)->build();

$loyaltyController = $client->getLoyaltyController();

try {
    $result = $loyaltyController->adjustLoyaltyPoints(
        $accountId,
        $body
    );
    echo 'AdjustLoyaltyPointsResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Search Loyalty Events

Searches for loyalty events.

A Square loyalty program maintains a ledger of events that occur during the lifetime of a
buyer's loyalty account. Each change in the point balance
(for example, points earned, points redeemed, and points expired) is
recorded in the ledger. Using this endpoint, you can search the ledger for events.

Search results are sorted by `created_at` in descending order.

```php
function searchLoyaltyEvents(SearchLoyaltyEventsRequest $body): SearchLoyaltyEventsResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`SearchLoyaltyEventsRequest`](../../doc/models/search-loyalty-events-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`LOYALTY_READ`

## Response Type

**200**: Success

[`SearchLoyaltyEventsResponse`](../../doc/models/search-loyalty-events-response.md)

## Example Usage

```php
$body = SearchLoyaltyEventsRequestBuilder::init()->build();

$loyaltyController = $client->getLoyaltyController();

try {
    $result = $loyaltyController->searchLoyaltyEvents($body);
    echo 'SearchLoyaltyEventsResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# List Loyalty Programs

Returns a list of loyalty programs in the seller's account.
Loyalty programs define how buyers can earn points and redeem points for rewards. Square sellers can have only one loyalty program, which is created and managed from the Seller Dashboard. For more information, see [Loyalty Program Overview](https://developer.squareup.com/docs/loyalty/overview).

Replaced with [RetrieveLoyaltyProgram](https://developer.squareup.com/reference/square_2021-08-18/loyalty-api/retrieve-loyalty-program) when used with the keyword `main`.

```php
function listLoyaltyPrograms(): ListLoyaltyProgramsResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Requires scope

### oauth2

`LOYALTY_READ`

## Response Type

**200**: Success

[`ListLoyaltyProgramsResponse`](../../doc/models/list-loyalty-programs-response.md)

## Example Usage

```php
$loyaltyController = $client->getLoyaltyController();

try {
    $result = $loyaltyController->listLoyaltyPrograms();
    echo 'ListLoyaltyProgramsResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Retrieve Loyalty Program

Retrieves the loyalty program in a seller's account, specified by the program ID or the keyword `main`.

Loyalty programs define how buyers can earn points and redeem points for rewards. Square sellers can have only one loyalty program, which is created and managed from the Seller Dashboard. For more information, see [Loyalty Program Overview](https://developer.squareup.com/docs/loyalty/overview).

```php
function retrieveLoyaltyProgram(string $programId): RetrieveLoyaltyProgramResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `programId` | `string` | Template, Required | The ID of the loyalty program or the keyword `main`. Either value can be used to retrieve the single loyalty program that belongs to the seller. |

## Requires scope

### oauth2

`LOYALTY_READ`

## Response Type

**200**: Success

[`RetrieveLoyaltyProgramResponse`](../../doc/models/retrieve-loyalty-program-response.md)

## Example Usage

```php
$programId = 'program_id0';

$loyaltyController = $client->getLoyaltyController();

try {
    $result = $loyaltyController->retrieveLoyaltyProgram($programId);
    echo 'RetrieveLoyaltyProgramResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Calculate Loyalty Points

Calculates the points a purchase earns.

- If you are using the Orders API to manage orders, you provide `order_id` in the request. The
  endpoint calculates the points by reading the order.
- If you are not using the Orders API to manage orders, you provide the purchase amount in
  the request for the endpoint to calculate the points.

An application might call this endpoint to show the points that a buyer can earn with the
specific purchase.

__Note:__ The country of the seller's Square account determines whether tax is included in the purchase amount when accruing points for spend-based and visit-based programs.
For more information, see [Availability of Square Loyalty](https://developer.squareup.com/docs/loyalty-api/overview#loyalty-market-availability).

```php
function calculateLoyaltyPoints(
    string $programId,
    CalculateLoyaltyPointsRequest $body
): CalculateLoyaltyPointsResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `programId` | `string` | Template, Required | The [loyalty program](https://developer.squareup.com/reference/square_2021-08-18/objects/LoyaltyProgram) ID, which defines the rules for accruing points. |
| `body` | [`CalculateLoyaltyPointsRequest`](../../doc/models/calculate-loyalty-points-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`LOYALTY_READ`

## Response Type

**200**: Success

[`CalculateLoyaltyPointsResponse`](../../doc/models/calculate-loyalty-points-response.md)

## Example Usage

```php
$programId = 'program_id0';

$body = CalculateLoyaltyPointsRequestBuilder::init()->build();

$loyaltyController = $client->getLoyaltyController();

try {
    $result = $loyaltyController->calculateLoyaltyPoints(
        $programId,
        $body
    );
    echo 'CalculateLoyaltyPointsResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Create Loyalty Reward

Creates a loyalty reward. In the process, the endpoint does following:

- Uses the `reward_tier_id` in the request to determine the number of points
  to lock for this reward.
- If the request includes `order_id`, it adds the reward and related discount to the order.

After a reward is created, the points are locked and
not available for the buyer to redeem another reward.

```php
function createLoyaltyReward(CreateLoyaltyRewardRequest $body): CreateLoyaltyRewardResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreateLoyaltyRewardRequest`](../../doc/models/create-loyalty-reward-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`LOYALTY_WRITE`

## Response Type

**200**: Success

[`CreateLoyaltyRewardResponse`](../../doc/models/create-loyalty-reward-response.md)

## Example Usage

```php
$body = CreateLoyaltyRewardRequestBuilder::init(
    'idempotency_key2',
    LoyaltyRewardBuilder::init(
        'loyalty_account_id0',
        'reward_tier_id6'
    )->build()
)->build();

$loyaltyController = $client->getLoyaltyController();

try {
    $result = $loyaltyController->createLoyaltyReward($body);
    echo 'CreateLoyaltyRewardResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Search Loyalty Rewards

Searches for loyalty rewards in a loyalty account.

In the current implementation, the endpoint supports search by the reward `status`.

If you know a reward ID, use the
[RetrieveLoyaltyReward](https://developer.squareup.com/reference/square_2021-08-18/loyalty-api/retrieve-loyalty-reward) endpoint.

Search results are sorted by `updated_at` in descending order.

```php
function searchLoyaltyRewards(SearchLoyaltyRewardsRequest $body): SearchLoyaltyRewardsResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`SearchLoyaltyRewardsRequest`](../../doc/models/search-loyalty-rewards-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`LOYALTY_READ`

## Response Type

**200**: Success

[`SearchLoyaltyRewardsResponse`](../../doc/models/search-loyalty-rewards-response.md)

## Example Usage

```php
$body = SearchLoyaltyRewardsRequestBuilder::init()->build();

$loyaltyController = $client->getLoyaltyController();

try {
    $result = $loyaltyController->searchLoyaltyRewards($body);
    echo 'SearchLoyaltyRewardsResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Delete Loyalty Reward

Deletes a loyalty reward by doing the following:

- Returns the loyalty points back to the loyalty account.
- If an order ID was specified when the reward was created
  (see [CreateLoyaltyReward](https://developer.squareup.com/reference/square_2021-08-18/loyalty-api/create-loyalty-reward)),
  it updates the order by removing the reward and related
  discounts.

You cannot delete a reward that has reached the terminal state (REDEEMED).

```php
function deleteLoyaltyReward(string $rewardId): DeleteLoyaltyRewardResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `rewardId` | `string` | Template, Required | The ID of the [loyalty reward](https://developer.squareup.com/reference/square_2021-08-18/objects/LoyaltyReward) to delete. |

## Requires scope

### oauth2

`LOYALTY_WRITE`

## Response Type

**200**: Success

[`DeleteLoyaltyRewardResponse`](../../doc/models/delete-loyalty-reward-response.md)

## Example Usage

```php
$rewardId = 'reward_id4';

$loyaltyController = $client->getLoyaltyController();

try {
    $result = $loyaltyController->deleteLoyaltyReward($rewardId);
    echo 'DeleteLoyaltyRewardResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Retrieve Loyalty Reward

Retrieves a loyalty reward.

```php
function retrieveLoyaltyReward(string $rewardId): RetrieveLoyaltyRewardResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `rewardId` | `string` | Template, Required | The ID of the [loyalty reward](https://developer.squareup.com/reference/square_2021-08-18/objects/LoyaltyReward) to retrieve. |

## Requires scope

### oauth2

`LOYALTY_READ`

## Response Type

**200**: Success

[`RetrieveLoyaltyRewardResponse`](../../doc/models/retrieve-loyalty-reward-response.md)

## Example Usage

```php
$rewardId = 'reward_id4';

$loyaltyController = $client->getLoyaltyController();

try {
    $result = $loyaltyController->retrieveLoyaltyReward($rewardId);
    echo 'RetrieveLoyaltyRewardResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Redeem Loyalty Reward

Redeems a loyalty reward.

The endpoint sets the reward to the `REDEEMED` terminal state.

If you are using your own order processing system (not using the
Orders API), you call this endpoint after the buyer paid for the
purchase.

After the reward reaches the terminal state, it cannot be deleted.
In other words, points used for the reward cannot be returned
to the account.

```php
function redeemLoyaltyReward(string $rewardId, RedeemLoyaltyRewardRequest $body): RedeemLoyaltyRewardResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `rewardId` | `string` | Template, Required | The ID of the [loyalty reward](https://developer.squareup.com/reference/square_2021-08-18/objects/LoyaltyReward) to redeem. |
| `body` | [`RedeemLoyaltyRewardRequest`](../../doc/models/redeem-loyalty-reward-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`LOYALTY_WRITE`

## Response Type

**200**: Success

[`RedeemLoyaltyRewardResponse`](../../doc/models/redeem-loyalty-reward-response.md)

## Example Usage

```php
$rewardId = 'reward_id4';

$body = RedeemLoyaltyRewardRequestBuilder::init(
    'idempotency_key2',
    'location_id0'
)->build();

$loyaltyController = $client->getLoyaltyController();

try {
    $result = $loyaltyController->redeemLoyaltyReward(
        $rewardId,
        $body
    );
    echo 'RedeemLoyaltyRewardResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

